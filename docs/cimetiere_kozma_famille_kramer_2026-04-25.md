# Cimetière israélite de Kozma utca (Budapest) — famille Kramer-Beck (recherches 25 avril 2026)

**Source** : base de données du cimetière, [database.budapestjewishcemetery.com](https://database.budapestjewishcemetery.com/) (Friends of Budapest Jewish Cemetery)

API découverte : `/wp-admin/admin-ajax.php?action=db_call&oper=search` (Angular 1.7.8, requiert nonce CSRF). 10 recherches parallèles en 1.5 s avec `curl &`.

## Notre famille au cimetière Kozma utca

### Tombe commune Zsigmond × Sarolta (parc. 15 / sor. 31 / sir. 20)

| Nom indexé | Naissance | Décès | Âge | ID base |
|---|---|---|---|---|
| **Kramer Zsigmond** | 1872 | 16 mai 1928 | 56 | 22605 |
| **Kramer Zsigmondné Beck Sarolta** | 1873 | 3 juillet 1937 | 64 | 22606 |

→ **Tombe commune** confirmée par l'endpoint `oper=moreinfo` (le serveur retourne les deux comme co-occupants de la même sépulture).

### Brunn Jozefa = Braun Jozefin (mère de Zsigmond) — tombe individuelle

| Nom indexé | Naissance | Décès | Âge | ID base | Tombe |
|---|---|---|---|---|---|
| **Kramer Árminné Braun Jozefin** | **1840** | **10 novembre 1925** | **85** | 91876 | parc. 40 / sor. 66 / sir. 20 |

**Date de décès précise** : **10 novembre 1925**. Tombe individuelle (Kramer Ármin n'est PAS à côté).

### Frank Mórné Kramer Julia (sœur de Zsigmond) — tombe individuelle

| Nom indexé | Naissance | Décès | Âge | ID base | Tombe |
|---|---|---|---|---|---|
| **Frank Mórné Kramer Julia** | 1877 | 21 octobre 1962 | 85 | 265765 | parc. 38/D / sor. 33 / sir. 26 |

### Kramer Lászlóné Stern Irén — ❌ HYPOTHÈSE INVALIDÉE 25.4.2026 soir

| Nom indexé | Naissance | Décès | Âge | ID base | Tombe |
|---|---|---|---|---|---|
| **Kramer Lászlóné Stern Irén** | **1899** | **16 janvier 1985** | **86** | 287008 | parc. U/1 / sor. 33 / sir. 18 |

**INVALIDATION (25 avril 2026, soir)** : la recherche FS Hungary Civil Registration sur László Kramer × Irén Stern retourne un **AUTRE** Krammer László :

> **Krammer László** — Death Registration **31 juillet 1954 Jászapáti**, Death **15 novembre 1944**, Parents **Weisz Rozália × Krammer Lipót**, Spouse **Stern Krammer Irén**

→ Stern Irén (1899-1985) est l'épouse de **CE Krammer László** (parents Weisz Rozália × Krammer Lipót, mort 15.11.1944), **et NON de notre Dr. László Kramer** (parents Zsigmond × Sarolta Beck, émigré au Brésil 1946 sous le nom Cantor).

→ La tombe individuelle parc.U/1 de Stern Irén à Kozma s'explique : son mari Krammer László † 15.11.1944 (probablement Shoah hongroise — la death registration différée à 1954 est typique des décès du génocide non documentés en temps réel). Pas de sépulture identifiée pour le mari.

**Conclusion** : l'épouse réelle de notre Dr. László Kramer reste **inconnue**. Possibilités : partie au Brésil avec lui en 1946 ; décédée avant 1946 ; non encore identifiée dans les registres hongrois.

## Membres de famille NON présents au cimetière Kozma

Recherches négatives (count=0) :

- **Kramer Ármin (notre, mari de Brunn Jozefa)** : pas trouvé. Décès entre 1901 (signataire faire-part Beck Gizella) et 1925 (Brunn Jozefa veuve à son décès). Lieu d'inhumation autre (autre cimetière israélite hongrois ? Nyitra ? Komárom ?).
- **Cantor** (László émigré Brésil 1946) : 0 résultats. Cohérent avec décès au Brésil.
- **Goldstein Lea** (= Lea Kramér × Jenő Goldstein 1936) : 0 résultats. Probable victime de la Shoah 1944 (déportée à Auschwitz comme la majorité des Juifs de Budapest), ou disparue / réfugiée.
- **Beck Nina / Nanetta** (2e épouse de Kramer Ármin) : 0 résultats. Pas inhumée à Kozma.
- **Perlhefter** (mari de Krammer Róza) : 0 résultats.
- **Krammer Juliánna 1896** (demi-sœur paternelle) : 0 résultats à Kozma.

## Méthodologie efficace

Les recherches de cette nuit ont démontré que la **base de données du cimetière Kozma** est **la ressource la plus rapide et la plus précise** pour localiser des inhumations juives à Budapest 1891-aujourd'hui. Endpoint utilisable directement par cURL :

```bash
NONCE="060f29038d"  # extrait du HTML de /hu/adatbazis-kereses/
curl -sL "https://database.budapestjewishcemetery.com/wp-admin/admin-ajax.php?\
action=db_call&_wpnonce=${NONCE}&oper=search&searchstr=NAME&\
pagenr=0&orderby=nev&order=ASC"
```

Performance mesurée : **10 recherches parallèles en 1.5 s** (cURL avec `&` + `wait`).

L'endpoint `oper=moreinfo&id=ID` retourne les co-occupants de la même tombe (parc/sor/sir), permettant d'identifier des couples ou parents inhumés ensemble.

## Pistes ouvertes après cette session

1. **Kramer Ármin (notre)** : son cimetière de décès — à chercher en dehors de Budapest. Hypothèses : Komárom (cimetière israélite), Nyitra (Slovaquie aujourd'hui Nitra), ou d'autres villes hongroises.
2. **Lea Kramér Goldstein 1902-?** : destin pendant la Shoah — Yad Vashem (Page of Testimony à chercher).
3. **Kramer Lászlóné Stern Irén** : si elle a eu une fille **Mária / Marishka**, c'est notre candidate principale pour la « Marishka » des années 80. À chercher dans BFL ou registres post-1985.
4. **Sámuel Kramer × Göttler Fanni 1924** : pas trouvé à Kozma — peut-être encore vivant après 1985 (born ~1880-1890, possible centenary), ou enterré ailleurs.

## CORRECTION 25 avril 2026 (soir) — Stern Irén RÉFUTÉ

### Stern Irén n'est PAS l'épouse de notre Dr. László Kramer

**Réfutation établie 25 avril 2026 (soir)** : la recherche FS Hungary Civil Registration `q.givenName=László&q.surname=Kramer&q.spouseGivenName=Irén&q.spouseSurname=Stern` retourne un AUTRE couple :

| Champ | Valeur |
|---|---|
| Name | **Krammer László** |
| Death | **15 novembre 1944** |
| Death Registration | **31 juillet 1954 Jászapáti**, Jász-Nagykun-Szolnok |
| Parents | **Weisz Rozália × Krammer Lipot** |
| Spouse | **Stern Krammer Irén** |

→ Cette Stern Irén est **clairement** l'épouse de Krammer László (parents Weisz/Lipót, mort 1944), **pas** de notre Dr. László (parents Zsigmond × Sarolta, parti au Brésil 1946).

**Indices concordants pour cette nouvelle interprétation** :
- Le mari Krammer László mort 15.11.1944 = période de la Shoah hongroise (déportations Auschwitz mars-juillet 1944, marches de la mort octobre-novembre 1944).
- Death registration différée à 1954 (10 ans) = signature typique des décès Shoah documentés a posteriori par survivants.
- Stern Irén veuve 1944, vit jusqu'en 1985, inhumée seule parc.U/1/33/18 — section moderne.
- Origine du couple Krammer Lipót × Weisz Rozália = pas notre famille Kramer-Beck-Brunn.

**Pour l'avis de décès de Sarolta Beck** (*Pesti Napló* 4.7.1937) qui cite « dr. Kramer Lászlóné menye » : l'épouse de notre Dr. László reste à identifier. Hypothèses :
1. Mariée à Budapest avant 1937, mais pas trouvée par cette recherche FS spécifique
2. Partie au Brésil avec László en 1946 (donc pas dans les registres hongrois post-1946)
3. Décédée avant 1946 sans descendance identifiée

**Action restante** : refaire la recherche FS sans le filtre `Stern` — chercher tous les Kramer László mariés à Budapest 1920-1946 dont l'épouse aurait pu accompagner le couple au Brésil.

### Kramer Ármin : où est-il enterré ?

Confirmé non inhumé à Kozma utca. Pistes par ordre de probabilité :

1. **Cimetière israélite de Komárom** (lieu d'origine de Sarolta Beck — possible aussi de Kramer Ármin par alliance) — base Komárom à explorer
2. **Cimetière israélite de Nyitra / Nitra** (lieu d'origine attribué de Kramer Zsigmond — pourrait l'être aussi pour Ármin) — registres slovaques
3. **Cimetière israélite de Pozsony / Bratislava** — registres slovaques
4. **Cimetière israélite Csörsz utcai (orthodoxe) à Budapest** — alternative à Kozma
5. **Cimetière israélite Salgótarjáni utcai** (un des 3 cimetières juifs de Pest)
6. **Décédé à l'étranger** (peu probable)

L'absence de sépulture commune avec Brunn Jozefa (parc.40/sor.66/sir.20, sépulture individuelle) suggère qu'il est mort **avant** elle (probablement 1900-1925) et inhumé séparément, ou ailleurs.

### Krammer Róza × Perlhefter Fábián †1933 : pas à Kozma non plus

0 résultats pour Perlhäfter / Perlhefter / Perlheffer dans la base Kozma. Donc inhumés ailleurs (cimetière israélite Csörsz, ou autre).

### Lea Kramér × Goldstein Jenő : pas à Kozma

0 résultats pour « Goldstein Jenőné Kramer Lea » ni pour « Kramer Lea ». 

**Hypothèse forte : victimes de la Shoah 1944**.
- Mariés 28.8.1936 Budapest, donc Juifs hongrois sous le régime Horthy puis Szálasi
- Pas de sépulture connue à Kozma ni Salgótarjáni
- À vérifier sur **Yad Vashem Names Database** (recherche manuelle JS, accès Chrome requis)
- À vérifier sur **MAZSIHISZ Holocaust victim register**

## Découverte additionnelle 25 avril 2026 (matin)

### Possible 5e sibling de Zsigmond : Rosenthall Miklósné née Kramer Mariska (1888-1928)

| Nom indexé | Naissance | Décès | Âge | ID | Tombe |
|---|---|---|---|---|---|
| **Rosenthall Miklósné Kramer Mariska** | **1888** | **28 juillet 1928** | **40** | 86432 | parc.39/sor.73/sir.51 |

**Hypothèse** : 5e enfant du couple Kramer Ármin × Brunn Jozefa, née tardivement (Brunn Jozefa avait 48 ans en 1888 — possible mais en limite biologique).

Cohérences :
- Inhumée à Kozma utca (cimetière familial)
- **Décédée 2 mois après son frère présumé Zsigmond** (16 mai 1928 → Mariska 28 juillet 1928) — sépulture similaire (Kozma) et chronologie proche
- Mariée à **Miklós Rosenthall** (non inhumé à Kozma — peut-être survivant ou ailleurs)
- Tombe individuelle parc.39 (différente de la parcelle 40 où repose Brunn Jozefa, mais Kozma utca compte 175 000 sépultures)

Incohérences ou faiblesses :
- Brunn Jozefa avait 48 ans en 1888 — possible mais l'âge maternel élevé est inhabituel
- Aucun acte de mariage Rosenthall × Kramer Mariska indexé sur OSZK ou FS
- Pas mentionnée sur le faire-part *Pesti Hírlap* 1928 de Zsigmond (« Dr. Majoros Ödönné és Kramer László gyermekei »… mais ces sont les *enfants*, pas les *frères/sœurs*)

→ **À confirmer par BFL Budapest** (acte de mariage Rosenthall × Kramer Mariska) ou **FS Hungary Civil Registration** (recherche : naissance Mariska Kramer 1888 Budapest, mère Brunn/Braun Jozefa).

## Résumé final famille Kramer-Brunn — recherches non résolues

| Personne | Inhumation Kozma ? | Lieu probable |
|---|---|---|
| Kramer Ármin (mari Brunn Jozefa) | NON | Komárom / Nyitra / Pozsony / autre cimetière israélite hongrois |
| Sámuel Kramer × Göttler Fanni 1924 | NON | Salgótarjáni / Csörsz / autre |
| Krammer Róza × Perlhefter Fábián †20.12.1933 | NON | Salgótarjáni / Csörsz / Rákoskeresztúr |
| Lea Kramér × Jenő Goldstein 1936 | NON | **Probable Shoah 1944** (Auschwitz) ; à vérifier Yad Vashem |
| Krammer Juliánna née 10.5.1896 (demi-sœur paternelle) | NON | À investiguer |
| Mariska Kramer × Miklós Rosenthall (5e sibling présumé) | OUI parc.39/73/51 | Kozma utca (Budapest) |
| Brunn Jozefa = Braun Jozefin (mère) | OUI parc.40/66/20 | Kozma utca |
| Kramer Zsigmond | OUI parc.15/31/20 | Kozma utca |
| Beck Sarolta | OUI parc.15/31/20 (commune) | Kozma utca |
| Frank Mórné Kramer Julia (sœur, †21.10.1962) | OUI parc.38/D/33/26 | Kozma utca |
| **Stern Irén** (parc.U/1/33/18, †1985) | OUI mais ❌ **PAS notre famille** — épouse Krammer László parents Weisz/Lipót †1944 (probable Shoah) | Kozma utca |
| Épouse réelle de notre Dr. Kramer László | INCONNUE | Brésil (avec László ?) ou décédée avant 1946 |
