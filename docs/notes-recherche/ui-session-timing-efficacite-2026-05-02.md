# Session Chrome UI 2 mai 2026 — timing et efficacité d'approches

## Contexte

Après que les 3 agents curl ont rapporté ce qu'ils pouvaient (FS bloqué auth, Hungaricana avec snippet SSR, Brésil mostly inaccessible), session UI Chrome pour vérifier ce qui restait.

## T0-T1 — durées observées

| Étape | Durée | Outil/approche |
|---|---|---|
| Création tab + navigation FS Records | 6 s | `tabs_create_mcp` + `navigate` + `wait` |
| Remplissage form (First+Last+Marriage event+Spouse) | ~30 s | `browser_batch` 6 actions (click+type) |
| `SEARCH` + résultats | 6 s | `wait` |
| Filter Marriage event dropdown | échec UI bug | `left_click` sur chip |
| Récupération list 492 hits | OK | screenshot direct |

## Comparaison curl vs UI vs browser_batch

### FamilySearch Records

| Approche | Résultat | Observation |
|---|---|---|
| **curl ARK direct** | 200 (shell React vide) | l'ARK existe (vs 404) mais pas de payload exploitable |
| **curl `service/search/hr/v3/personas`** | 403 Forbidden | API auth-required |
| **curl `platform/records/...`** | 403/401 | API auth-required |
| **UI form via browser_batch** | ✓ Listes hits visibles | mais form fields sensibles aux clics imprécis |
| **URL directe `/search/record/results?q.*=*`** | « Something Went Wrong » | URL bricolée triggers cet écran d'erreur ; toujours **passer par UI form** (cf. `feedback_familysearch_ui_vs_url.md`) |
| **URL `/search/collection/{id}?q.*=*`** | ✓ Page collection + form | mais filter non appliqué via query string ; il faut re-saisir et click SEARCH |

### FamilySearch Tree / Catalog

| Approche | Résultat | Observation |
|---|---|---|
| `/tree/person/details/<GID>` | OK shell rendu en UI | charge ~5s, screenshot après wait fonctionne |
| `/search/film/<DGS>` | OK image viewer | thumbnails chargés dynamiquement |
| `/search/catalog/results?q.place=*` | OK liste catalogue | autocompletion des places à respecter dans dropdown |

### Hungaricana ADT

| Approche | Résultat | Observation |
|---|---|---|
| **curl `library.hungaricana.hu/hu/search/results`** | ✓ HTML SSR avec `<div class="list-group-item">` | parsable directement, ~20 hits/page |
| **curl `adtplus.arcanum.com/hu/api/search-info`** | JSON utile | endpoint fonctionne sans auth |
| **UI page article** (`adt.arcanum.com/hu/view/...`) | breadcrumb + snippet visible | image complète **nécessite abonnement** ("Önnek nincs aktív előfizetése") |

### Yad Vashem Names DB

| Approche | Résultat | Observation |
|---|---|---|
| curl `collections.yadvashem.org` | TLS error / refuse User-Agent | inaccessible automatisé |
| **UI `yvng.yadvashem.org/?lastName=...&firstName=...`** | URL params **NON appliqués** | navigation se fait mais form vide ; nécessite vraie saisie interactive |

### Brazil sources

| Source | Approche | Résultat |
|---|---|---|
| WorldCat | curl/fetch | 403 systématique |
| DNB (Allemagne) | curl/fetch | OK 43 notices Majoros Ferenc |
| **APESP `arquivoestado.sp.gov.br`** | front-end JS | nécessite browser interactif |
| Hevra Kadisha SP | front-end JS | nécessite browser interactif |
| JUCESP | API auth e-CPF | inaccessible |
| Arquivo Nacional (SIAN) | captcha | inaccessible automatisé |

## Findings concrets de la session UI

### A. FS Records — confirmation de l'index BFL

- **Recherche « Ödön Majoros + Marriage Budapest »** : **492 hits** dont :
  - Line 2 : « Majoros Ödön » Death Reg 15.8.1966 + Birth 1884 + Spouses **Kramer Majoros Mária** + Parents **Heiduska Zsófia, Majoros József** ✓ = notre Ödön (record déjà connu : ARK `1:1:6V1G-YBG3`)
  - Mais **l'événement mariage 1918 lui-même n'est pas indexé** comme record propre — seul le décès 1966 est dans l'index FS aujourd'hui.
- **Recherche dans collection « Brazil, São Paulo, Immigration Cards 1902-1980 » (id 2140223)** :
  - First Name « Ladislas » + Last Name « Kantor » + Birth 1903 → **0 résultat**
  - Last Name seul « Kantor » → 1 résultat (« Concepcion Anaya **Cantero** » ≠ Kantor)
  - Father « Sigismundo Kramer » + Birth 1903 → 0 résultat

### B. ARK Kantor 1947 — RÉVISION

- **L'ARK `1:1:69VG-XPNZ` du package Michel renvoie HTTP 404** aujourd'hui (« Page Not Found » depuis l'UI).
- Sur le screenshot Michel daté du Fri Mar 08 2026 (capture FS), l'ARK `69VG-XPNZ` était valide ET indexait Ladislas Kantor avec le sexe **erroné « Female »** + autres détails (Sigismundo Kramer + Charlotte Beck).
- La collection 2140223 est listée comme « partiellement indexée » : *Some of these records have been indexed and are searchable as part of this collection. Additional images and indexes will be published as they become available.*
- **Hypothèse** : FS a re-indexé entre mars et mai 2026 — l'ARK ancien est obsolète, le nouvel ARK n'est pas immédiatement trouvable par recherche nominative.

### C. Hungaricana ADT — confirmation Almanach ELTE 1903-04

- URL : `https://adt.arcanum.com/hu/view/ELTE_Almanach_1903/?query=%22Montag%20%C3%96d%C3%B6n%22%20joghallgat%C3%B3&pg=144`
- Breadcrumb : « Az Eötvös Loránd Tudományegyetem évkönyvei → A Budapesti Királyi Magyar Tudomány-Egyetem almanachja, **1903-1904** → Egyetemi hallgatók »
- Search panel : **1 hit** « JOGHALLGATÓK 145 Név Beikt[atás] (...) Monó Ferencz 98 I ii **Mont... Ödön 903 i ii** Montbach Jenő (...) » — **CONFIRMÉ**
- Image complète bloquée (« Önnek nincs aktív előfizetése »), mais le snippet du panneau de recherche suffit à valider l'agent's finding.

### D. Pesti Hírlap 1905-08-26

- URL : `https://adt.arcanum.com/hu/view/PestiHirlap_1905_08/?query=%22Montag%20%C3%96d%C3%B6n%22%20Zenta&pg=672`
- Breadcrumb : « Pesti Hírlap, 1905. augusztus (27. évfolyam, 211-241. szám) → 1905-08-26 / 236. szám » — **page exacte trouvée**
- Image bloquée par paywall mais l'existence du hit est confirmée.

## Recommandations méthodologiques

### Hiérarchie d'approches selon source

1. **Hungaricana ADT** : utiliser **curl** (HTML SSR exploitable, snippets riches). Vérification UI utile uniquement pour breadcrumb + page exacte.
2. **FamilySearch** : **toujours UI form** (pas d'URL bricolée). Si bloqué auth (curl), réserver à navigateur interactif. Cf. `feedback_familysearch_ui_vs_url.md`.
3. **Yad Vashem / Arolsen / DEGOB** : **UI interactif obligatoire** (URL params non honorés, JS rendering).
4. **Cartórios / JUCESP / SIAN brésiliens** : abandonner sans accès payant ou e-CPF — déléguer à correspondant brésilien.

### Patterns gagnants browser_batch

- **Préfixer chaque batch par un screenshot** au cas où le tab a freezé entre-temps
- **Limiter à 6-8 actions par batch** : au-delà, risque de timeout CDP cumulé
- **Utiliser `wait` 5-8 sec après navigate** : FS et Hungaricana mettent du temps à hydrater le React/JS

### Patterns à éviter

- **`Ctrl+0` zoom reset après plusieurs interactions** : déclenche systématiquement un timeout CDP (testé)
- **Cliquer sur un dropdown FS sans wait** : items pas encore chargés → mauvaise sélection
- **Fermer un tab figé sans tabs_context_mcp préalable** : Chrome auto-supprime le groupe et la session continue ailleurs (vu sur tab 433271720 → 433271723)

## Pistes pour suite

1. **Récupérer le bon ARK Kantor 1947** : navigation Browse via Image Group de la collection 2140223 (`https://www.familysearch.org/search/film/...`) en cherchant les images de cartões 1947.
2. **Trouver acte naissance László 20.4.1903 Bp** : chercher en collection 1452460 Hungary CR Births sans surname (juste père Zsigmond Kramer + mère Beck Sarolta + 1903).
3. **Yad Vashem Bokor Panni** : session navigateur dédiée avec saisie manuelle (l'agent UI automatisé bute sur le rendering JS).
4. **Hungaricana abonnement** : pour images HD des hits ADT (magyarisation 1905, ELTE Almanach 1903, etc.) — à acquérir si on veut les preuves photographiques au-delà des snippets.

## Inhibiteur de mise en veille

Active depuis 2 mai 2026 ~00:13, pour 13h (jusqu'au 2.5.2026 ~13:13). PID 98873.
