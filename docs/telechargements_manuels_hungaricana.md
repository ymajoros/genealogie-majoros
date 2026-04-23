# Téléchargements manuels à effectuer

**Objet** : pièces d'archives identifiées en ligne mais **non encore téléchargées en fac-similé**, à récupérer manuellement. Chaque entrée donne l'**URL exacte** du viewer Hungaricana (avec `pg=` pointé), la page imprimée visée, et un nom de fichier suggéré pour le dépôt dans `actes/archives-web/`.

Dernière mise à jour : 2026-04-23.

---

## ⚠ Contraintes techniques

### Hungaricana — library.hungaricana.hu

- **CDN signée** : les fac-similés JPEG pleine résolution (`/pdf1/…/large/pageNNNN.jpg`) **ne sont pas accessibles** en curl/WebFetch.
- **Canvas PDF.js** : capture possible via la console navigateur (`canvas.toBlob()`), **mais Chrome limite à un download programmatique par user-gesture** — un seul download automatisé par session.
- **Bouton « Save pages »** (icône ↓ à droite de la barre d'outils du viewer) : fonctionne, **reCAPTCHA obligatoire**, max **25 pages par export**. C'est la méthode recommandée.

### OSZK Gyászjelentések — dspace.oszk.hu

- Accès libre, pas d'authentification.
- Chaque fiche expose `*_mormon.jpg` (fac-similé) et `*_work.txt` (OCR).
- Pattern direct curl :
  ```
  https://dspace.oszk.hu/bitstream/handle/20.500.12346/{handleID}/{archiveFile}_mormon.jpg
  https://dspace.oszk.hu/bitstream/handle/20.500.12346/{handleID}/{archiveFile}_work.txt
  ```

---

## A. Hungaricana — à exporter (Save pages + reCAPTCHA)

### A.1 **BPSZKJ_1909** — Budapest főváros törvényhatósági bizottsága közgyűlési jegyzőkönyvei, séance 23 juin 1909

- URL document : https://library.hungaricana.hu/en/view/BPSZKJ_1909/
- URL direct (pg= à vérifier par recherche « szinóbányai Kramer Jakab » dans le viewer) : les pages imprimées sont **1268, 1269, 1270, 1271**.
- **Contenu** : fondation établie par szinóbányai Kramer Jakab × Hirsch Janka, acceptée et remerciée par le conseil municipal.
- Nom de fichier suggéré : `BPSZKJ_1909_pp1268-1271_Fondation_Jakab_Janka.pdf`
- **Correction** : le fichier `BPSZKJ_1909__pages806-806.pdf` déjà archivé correspond à la **table des matières**, pas à la séance elle-même.

### A.2 **FszekCimNevTarak_20_019_01** — Annuaire téléphonique Budapest 1929 mai, section « K »

- URL : https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_01/?pg=255&layout=s
- Pages : **224 imprimée** (viewer pg=255), suivante pg=256.
- **Contenu** :
  - **Leó szinóbányai** Aut 246-29, VI. Bajza-u. 2 (domicile, locataire Bruchsteiner Fedor)
  - **Mór szinóbányai** Aut 834-39, IV. Irányi-u. 21
  - **Krámer Rezső és társa likőr-, rum- és konyakgyára** Aut 243-67, V. Tátra-u. 4
  - Samuné özv. ▲L 978-75, V. Honvéd-u. 18
  - Krámer Sámuel, V. Wekerle Sándor-u. 18
  - Krámer testvérek elektromos (Zoltán) ▲L 982-26, VI. Podmaniczky-u. 13
  - Kramer József posthume — Kramer Józsefné orvosi kozmetikai int.
  - **Pas d'entrée Kramer Zsigmond** (décédé mai 1928).
- Nom de fichier suggéré : `FszekCimNevTarak_1929_pp224-225_Kramer_K.pdf`

### A.3 **ORSZ_BPTM_TBM_17** — Tanulmányok Budapest Múltjából XVII (1966), Vörös Károly, « Budapest legnagyobb adófizetői 1903-1917 »

- URL document : https://library.hungaricana.hu/en/view/ORSZ_BPTM_TBM_17/
- Pages viewer : **pg=173-174** (Leó szinóbányai gendre Fürst Bertalan ; mariage dans l'élite juive Fürst-Krausz-Brüll) et **pg=182-183** (Jakab szinóbányai parmi les grands contribuables avec baron Madarassy Beck, malomszegi Elek Pál, Hajós József).
- URL précise : https://library.hungaricana.hu/en/view/ORSZ_BPTM_TBM_17/?query=%22szin%C3%B3b%C3%A1nyai%20Kramer%22&pg=173&layout=s
- Nom de fichier suggéré : `Tanulmanyok_BpMultjabol_17_pp172-183_Kramer_Fürst.pdf`

### A.4 **Lapszemle_1930_09** — mention fonderie Szinóbánya 300 ouvriers

- URL document : https://library.hungaricana.hu/en/view/Lapszemle_1930_09/
- Page à exporter : autour de **pg=1366** (le numéro 1930-09-18 dans ce mensuel qui en contient ≈1450 pages).
- URL directe : https://library.hungaricana.hu/en/view/Lapszemle_1930_09/?pg=1366&layout=s
- **Contenu** : mention de « a Kramer-féle szinóbányai vasgyár » employant 300 ouvriers.
- Nom de fichier suggéré : `Lapszemle_1930_09_18_pg1366_Szinobanya_fonderie.pdf`
- **Note** : *Lapszemle* est un bulletin de presse hongrois (Magyar Távirati Iroda revue de presse) et contient ~1400+ pages par mois — ne pas tenter d'exporter plus que la page concernée.

### A.5 **ORSZ_SKAN_He_10** — Ház és ember, évkönyv 10 (Szentendre, 1995)

- URL document : https://library.hungaricana.hu/en/view/ORSZ_SKAN_He_10/
- Page : **131** (Sabján Tibor, « A takaréktűzhely meghonosodása a magyar parasztságnál »)
- URL directe : https://library.hungaricana.hu/en/view/ORSZ_SKAN_He_10/?pg=131&layout=s
- **Contenu** : mention du catalogue illustré *Kramer Szinóbányai vasgyárának képes árjegyzéke 1895*.
- Nom de fichier suggéré : `HazEsEmber_10_pg131_Kramer_vasgyar_1895.pdf`

### A.6 **SZAK_TEXT_Ek_11_2003** — Textil-és Textilruházati Ipartörténeti Múzeum Évkönyve XI (2003)

- URL document : https://library.hungaricana.hu/en/view/SZAK_TEXT_Ek_11_2003/
- Page : **87** (Tóth György, « Vasalók »)
- URL directe : https://library.hungaricana.hu/en/view/SZAK_TEXT_Ek_11_2003/?pg=87&layout=s
- **Contenu** : fers à repasser de tailleur (*szabóvasaló*) produits par la fonderie Szinóbánya.
- Nom de fichier suggéré : `TextilEvkonyv_11_pg87_Kramer_vasalok.pdf`

### A.7 **SZTNH_KozpontiErtesito_1897** — inscription commerciale Kramer Zsigmond 12 mars 1897

- URL document : https://library.hungaricana.hu/en/view/SZTNH_KozpontiErtesito_1897/
- Page imprimée : **339** (viewer pg=338)
- URL directe : https://library.hungaricana.hu/en/view/SZTNH_KozpontiErtesito_1897/?pg=338&layout=s
- **Contenu** : enregistrement au tribunal de commerce de Budapest, 12 mars 1897, inscriptions 7938/1 et 7910/1 :
  > *Kramer Zsigmond, likőr, rum, cognac és különféle szeszes italok gyári raktára üzlettulajdonos, budapesti lakos — czégvezető : Pánisz Sándor, fakereskedő, Szent-Endrei lakos.*
- Nom de fichier suggéré : `KozpontiErtesito_1897_pg339_Kramer_Zsigmond_inscription.pdf`

### A.8 **BPLAKCIMJEGYZEK_29_1928** — Kramer Zsigmond VIII Tisza Kálmán tér 28

- URL document : https://library.hungaricana.hu/en/view/BPLAKCIMJEGYZEK_29_1928/
- Page : **1 846**
- URL directe : https://library.hungaricana.hu/en/view/BPLAKCIMJEGYZEK_29_1928/?pg=1846&layout=s
- **Contenu** : « Kramer Zsigmond VIII Tisza Kálmán tér 28 » dans la section F) Gyárosok, iparosok és kereskedők czímjegyzéke.
- Nom de fichier suggéré : `BPLAKCIMJEGYZEK_1928_pg1846_Kramer_Zsigmond_Tisza_Kalman.pdf`

### A.9 **SZTNH_KozpontiErtesito_1895** — Kramer Lipót Leo associé

- URL document : https://library.hungaricana.hu/en/view/SZTNH_KozpontiErtesito_1895/
- Déjà partiellement archivé (fichier local `SZTNH_KozpontiErtesito_1895-1612054939__pages345-345.pdf`) — à revérifier pour éventuel complément.

---

## B. Annuaires téléphoniques Budapest — série chronologique

Collection Hungaricana : https://library.hungaricana.hu/en/collection/fszek_budapesti_telefonkonyvek/

| ID document | Date | URL viewer | Section K (Kramer) |
|---|---|---|---|
| `FszekCimNevTarak_20_00_1906` | nov. 1906 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1906/ | à localiser |
| `FszekCimNevTarak_20_00_1912` | sept. 1912 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1912/ | p. 276 imprimée |
| `FszekCimNevTarak_20_00_1913` | déc. 1913 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1913/ | p. 242 imprimée |
| `FszekCimNevTarak_20_00_1914` | juin 1914 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1914/ | p. 251 imprimée |
| `FszekCimNevTarak_20_00_1917` | 1917 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1917/ | p. 1_256 |
| `FszekCimNevTarak_20_00_1920` | mai 1920 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_00_1920/ | p. 302 imprimée (viewer pg=324) — **✓ archivé** |
| `FszekCimNevTarak_20_019_01` | mai 1929 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_01/ | p. 224 imprimée (pg=255) |
| `FszekCimNevTarak_20_019_03` | mai 1939 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_03/ | p. 1_238 |
| `FszekCimNevTarak_20_019_04` | sept. 1940 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_04/ | p. 1_258 |
| `FszekCimNevTarak_20_019_06` | juin 1941 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_06/ | (professions) |
| `FszekCimNevTarak_20_019_04_00_1942` | 1942 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_04_00_1942/ | p. 1_277 — **✓ p. 518 archivé** |
| `FszekCimNevTarak_20_019_04_00_1943_01` | janv. 1943 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_04_00_1943_01/ | p. 296 |
| `FszekCimNevTarak_20_019_05` | avril 1945 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_05/ | (post-Shoah — critique pour retracer les survivants) |
| `FszekCimNevTarak_20_019_12` | mars 1948 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_12/ | (post-guerre) |
| `FszekCimNevTarak_20_019_14` | déc. 1950 | https://library.hungaricana.hu/en/view/FszekCimNevTarak_20_019_14/ | (époque nationalisation) |

**Priorité recommandée** :
- **1929** pour arbitrage Rezső és társa vs Zsigmond.
- **1945** (avril) et **1948** pour tracer les survivants Shoah (Emil dr, Felix, Jenő, Ottilia, László Kramer).

---

## C. OSZK Gyászjelentések — à compléter

Les faire-part suivants **ne sont pas indexés** sous leur nom simple dans DSpace OSZK mais peuvent l'être sous orthographe variante. À retester :

| Cible | Requête à tester | URL base |
|---|---|---|
| **Kramer Jakab** (szinóbányai) † 1919 | `"szinóbányai Kramer Jakab"`, `"Krámer Jakab"` | https://dspace.oszk.hu/handle/20.500.12346/663648/discover |
| **Kramer József** (szinóbányai) † avant 1919 | `"szinóbányai Kramer József"`, `"Krámer József"` | — |
| **Kramer Rezső / Rudolf** (szinóbányai) | `"szinóbányai Kramer Rezső"` | — |
| **Kramer Dávid Tivadar / Theodor** | `"Krámer Tivadar"` | — |
| **Kramer Lipót Leó** † 1921 | `"Krámer Leó"`, `"Kramer Lipót"` | — |
| **Kramer Zsigmond** † 16.05.1928 | `"Krámer Zsigmond"` | — |
| **Kramer Ottilia** (fille de Tivadar, post-1916) | `"Krámer Ottilia"`, `"szinóbányai Kramer Ottilia"` | — |
| **Weinberger Jakabné Kramer Cecília** | `"Weinberger"` + Cecília + Kramer | — |

---

## D. Arcanum ADT — presse hongroise 1800-1950 (payant)

URL : https://adt.arcanum.com/en/search/?query=

| Requête | Publication / année | Objet |
|---|---|---|
| `"szinóbányai Kramer Jakab"` | *Pesti Hírlap*, *Az Est*, *Budapesti Hírlap* 1919 | Nécrologie de Jakab |
| `"szinóbányai Kramer József"` | Presse Szeged / Budapest 1906-1919 | Nécrologie de József |
| `"szinóbányai Kramer Rezső"` | — | Nécrologie de Rezső |
| `"szinóbányai Kramer Leó"` | 1921 | Nécrologie de Leó |
| `"Kramer Zsigmond"` + decès | *Pesti Hírlap* 17 mai 1928 | Avis mortuaire Zsigmond |
| `Egyenlőség` + Kramer | 1882-1938 | Hebdomadaire juif — parcours complet |

---

## E. FamilySearch — actes d'état civil

Collection **Hungary, Civil Registration 1895-1980** : https://www.familysearch.org/search/collection/1452460 (gratuit, compte requis).

Cibles prioritaires :

1. **Acte de décès Zsigmond Kramer 16.05.1928 Budapest** — filiation, lieu de naissance (Nyitra).
2. **Acte de décès Sarolta Beck ~juillet 1937 Budapest**.
3. **Acte de décès Jakab Kramer 1919 Budapest** — district IV (Sütő-u. 2 en 1920).
4. **Acte de décès Leó Kramer 1921 Budapest** — VI. Bajza-u. 2.
5. **Acte de décès József Kramer (1906-1919) Budapest**.
6. **Acte de mariage Kramer Mária × Majoros Ödön (= Montag Ödön) Budapest ~1918**.
7. **Actes de naissance des enfants de Jakab × Hirsch Janka** : Tivadar (1861), Rosalie (1866), Leó (1869), Mór (1870), Hugo, Oszkár, Jenny.

Destination : `actes/familysearch/`

---

## F. Slovenský národný archív — Matrikel juifs de Nitra

Archives slovaques (Bratislava) — fonds communauté israélite de **Nitra (Nyitra)**. Consultation sur place.

Cibles :
- Naissance **Zsigmond Kramer** (estimation 1850-1870).
- Fratrie de Zsigmond (test de l'hypothèse cousinage avec Ignácz).
- Fratrie éventuelle d'Ignácz Kramer (génération précédente).

---

## G. Yad Vashem — Pages of Testimony

URL : https://yvng.yadvashem.org/

Cibles :
- **Kramer Ottilia szinóbányai** (fille de Tivadar, née ≈1890-1895)
- **Kramer Emil dr** (kormányfőtanácsos 1940-1943)
- **Kramer Felix, Ernő, Ignácz-Pál, Jenő** (dernière apparition 1943)
- **Krámer László** (fils de Zsigmond, étudiant 1922, sort après-1945 ?)
- **Krámer Mária** (fille de Zsigmond, épouse Majoros Ödön — sort après-Shoah selon témoignage direct Yannick : décès vers 1983 à Budapest)

---

## H. Instructions pratiques — Hungaricana « Save pages »

1. Ouvrir l'URL directe du document avec `?pg=X&layout=s`.
2. Attendre le chargement complet du canvas.
3. Cliquer l'icône **↓** (Save pages) à droite de la barre d'outils.
4. Saisir **From: X**, **To: Y** (max 25 pages par export).
5. Cocher le reCAPTCHA, cliquer **OK**.
6. Le PDF se télécharge dans `~/Downloads/` avec le nom `<ID>__pagesX-Y.pdf` — à renommer et déplacer dans `actes/archives-web/hungaricana/`.

Pour optimiser le nombre de captchas : **regrouper plusieurs pages consécutives** dans le même export (ex. pg=64-70 en une fois pour Tanárképző plutôt que deux exports pg=64-66 et pg=67-70).
