# Recherche FS : mariage Ármin × Brunn Jozefa + parents d'Ármin (26.4.2026 soir)

## Méthode

FS Records search via UI (formulaire panneau droit, pas URL bricolée — feedback Yannick 26.4.2026 : « Something Went Wrong » = symptôme d'URL construite à la main).

## Recherche A — Hermann Kramer × Josefine Braun (mariage attendu ~1862-1864)

Requête UI :
- First Names : Hermann
- Last Names : Kramer
- Spouse First Names : Josefine
- Spouse Last Names : Braun
- (Show Exact Search : OFF)

→ **109 438 résultats**, dominés par homonymes mondiaux. Filtre Marriage event annonce 44 mariages en Continental Europe, mais aucun ne correspond à Hermann Kramer × Brunn Jozefa.

Top 9 hits = nos 7 enfants (Netti, Regi×2 doublon, Sigmund, Sali, Julie, Isák, Adolf) — tous BIRTH events à Ujlak où Hermann figure comme père. **Aucun acte de mariage indexé.**

**Conclusion A** : le mariage Ármin × Jozefa ~1862-1864 **n'est PAS indexé dans Hungary Jewish VR Index 1800-1945** (collection 1857881). Soit l'index n'a pas saisi cette période/section du registre Nitra, soit le mariage a eu lieu hors de Nyitra (Komárom ? Pest ?).

## Recherche B — Hermann Kramer naissance Nyitra ~1825-1850 (parents inconnus)

Requête UI :
- First Names : Hermann
- Last Names : Kramer
- Birth Place : Nyitra, Hungary (county top-level)
- Birth Year : 1825-1850 (filtre non appliqué — UI bug ?)

→ **152 résultats**, mais tous Hermann/Hermá/Herrman Kramer comme **père** (pas comme principal/bébé), couples notamment :
- **Hermann Kramer × Weinberger Rosalie** — enfants Bertha, Elias, David, Netti, Philipp (couple cousin probable identifié antérieurement)
- **Kramer Hermá × Zweig Rosá** — enfant Pauline
- **Hermann Kramer × Lilly Davis** (homonyme USA)
- **Hermann Kramer × Rosy** — enfant Netty

**Aucune naissance Hermann Kramer enfant** à Nyitra dans cet index.

**Conclusion B** : Hungary Jewish VR Index 1800-1945 **ne couvre pas les naissances 1820-1850 à Nyitra**. La période 1850-1895 est bien indexée (cf. nos 7 enfants), mais 1820-1850 manque.

## Implication

Pour identifier les parents d'Ármin (b ~1830-1845), il faut chercher hors de l'index FS :

1. **Folder antérieur du registre juif de Nitra** sur FS Catalog (avant 1850) — l'identifier puis browse images directement
2. **Slovenský národný archív Nitra** : registres israélites communauté juive de Nitra antérieurs à 1850
3. **Trees externes** : Geni / MyHeritage / Geneanet — recherche Krámer Hermán × Brunn Jozefa Ujlak

## Couples Krämer/Kramer identifiés à Nyitra (homonymes ou cousins ?)

| Père | Mère | Période enfants | Lien probable |
|---|---|---|---|
| **Hermann Kramer** | Brunn/Braun Jozefa | 1865-1881 Ujlak | **= notre Ármin/Hermán** |
| **Hermann Kramer** | Weinberger Rosalia | ~1865-1880 Nyitra | cousin probable (Netti 1867, Bertha, Elias, David, Philipp) |
| Hermá Kramer | Zweig Rosá | (date inconnue) | possible cousin |
| Hermann Kramer | Rosy | (date inconnue) | possible cousin |

**À investiguer** : recouper la fratrie de Hermann Kramer × Weinberger Rosalia sur cet index — si parents communs (= grands-parents d'Ármin), l'identification serait directe.

## Note méthodologique — leçon apprise

⚠️ **Ne jamais construire à la main une URL FS Records** (`/search/record/results?q.surname=...`) — déclenche systématiquement l'écran « Something Went Wrong ». Toujours :
1. Naviguer vers la page racine `/search/record/results`
2. Remplir le formulaire UI (panneau droit)
3. Cliquer SEARCH
4. Laisser FS générer l'URL valide

Cette règle s'applique aussi au catalogue, à Full-Text et probablement à toutes les pages FS de recherche.

## Tâches encore ouvertes (à reporter en session manuelle)

1. **Identifier le folder FS antérieur 1820-1850 Nitra Jewish** via catalogue Slovak Republic > Nitra > Jewish — puis browse pour acte naissance Ármin
2. **Hermann Kramer × Weinberger Rosalia** : extraire fratrie complète (acte mariage ou naissance des parents)
3. **Mariage Ármin × Jozefa** : chercher dans folder Nitra 004542024 Item 6 section mariages (images ~100-133), browse direct
4. **Acte décès civil Krámer Ármin †17.8.1927 Bp** : BFL via image group (collection 1452460 ne couvre pas 1927)
5. **Acte décès civil Krämer Izsák †15.5.1957 Bp** : idem (1957 hors couverture)
