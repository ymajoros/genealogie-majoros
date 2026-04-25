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

### Kramer Lászlóné Stern Irén — épouse probable de notre Dr. László Kramer

| Nom indexé | Naissance | Décès | Âge | ID base | Tombe |
|---|---|---|---|---|---|
| **Kramer Lászlóné Stern Irén** | **1899** | **16 janvier 1985** | **86** | 287008 | parc. U/1 / sor. 33 / sir. 18 |

**Hypothèse** : épouse de notre Dr. **Kramer László** (1900?-? Brésil), restée à Budapest après son émigration au Brésil en 1946 (László → Cantor à São Paulo per témoignage Michel Majoros).

→ Stern Irén est **seule dans sa tombe** (parcelle U/1 = section ajoutée dans les années 1970-80). Cohérent avec un mari ailleurs (Brésil).

→ **Si Marishka (visiteuse années 80s) était une fille de László × Stern Irén**, elle serait nièce de Maria et cousine de Ferenc. Stern Irén morte 1985 à 86 ans (née 1899) → enfants probables nés 1920-1940.

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

## CORRECTION 25 avril 2026 (matin)

### Stern Irén = épouse de notre Dr. László Kramer ? À CONFIRMER

**Le rattachement n'est PAS établi avec certitude.** Les indices concordants :

- L'avis de décès de Sarolta Beck (*Pesti Napló* 4.7.1937) cite « **dr. Kramer Lászlóné menye** » (sa belle-fille, donc épouse de László) sans la nommer.
- Une seule **Kramer Lászlóné Stern Irén** (1899-1985) est inhumée à Kozma utca, parc.U/1/sor.33/sir.18.
- László a émigré au Brésil en 1946 (« sous le nom de Cantor » selon Michel Majoros).
- Stern Irén † 1985 à Budapest, donc **n'a pas suivi** à São Paulo si elle est notre belle-grand-tante.

**Mais** :
- Plusieurs **Kramer László** existaient à Budapest dans cette génération (homonymie courante).
- Sans **acte de mariage civil** (BFL Budapest) ou **acte de décès Stern Irén** (1985) qui nomme explicitement le mari, le rattachement reste hypothétique.
- Il est aussi possible que la véritable épouse de notre Dr. László l'ait accompagné au Brésil et n'apparaisse pas dans les registres hongrois.

**Action requise** : récupérer l'acte de décès de Stern Irén 1985 sur FS Hungary Civil Registration (qui couvre jusqu'à 1980, donc 1985 est limite — possible ou pas) ; ou consulter BFL pour acte de mariage Kramer László × Stern Irén.

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
