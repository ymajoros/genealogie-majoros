# UI session — recherche acte naissance László Kramer 20.4.1903 Bp

## Méthode

URL bricolée **AVEC scope collection FS** :
```
https://www.familysearch.org/search/record/results?q.givenName=László&q.surname=Kramer&q.birthLikeDate.from=1903&q.birthLikeDate.to=1903&q.fatherGivenName=Zsigmond&q.fatherSurname=Kramer&q.motherGivenName=Sarolta&q.motherSurname=Beck&f.collectionId=1452460
```

→ **43 résultats trouvés** dans Hungary, Civil Registration 1895-1980. Toutes les entrées montrent László Kramer comme **Father / Other / Father Of Groom** dans des actes ultérieurs ; **aucune ne le montre comme principal d'une naissance 1903**.

⭐ **Découverte méthodologique** : URL bricolée FONCTIONNE quand scopée à une collection (`f.collectionId=1452460`). Le « Something Went Wrong » survient seulement quand la requête traverse trop de collections sans scope.

À mettre à jour dans `feedback_familysearch_ui_vs_url.md`.

## Hits notables (échantillon top 11)

| Rôle | Krámer/Kramer László | Spouse | Children |
|---|---|---|---|
| Father | Krámer László | Buchora Zsuzsánna | Krámer László (homonyme) |
| Other | Kramer László | Steinfeld Gizella | Kramer Andor |
| Other | Kramer László | Heinfeld | Kramer Andor |
| Father | Kremsner László | Frühmann Ágnes | Kremsner József |
| Father | Krammer László | Bogdán Verona | Krammer Mihály |
| Father | Krammer László | Bogdán Verona | Krammer István |
| Father | Kremsner László | Frühmann Ágnes | Kremsner József |
| Father | Kremer László | Csóko Ágnes | Kremer Anna |
| Father | Krémer László | Csóka Ágnes | Krémer József |
| Father Of Groom | Kremer László | Csóka Ágnes | Kremer Béla Lajos |
| Father | Kremer László | (...) | (...) |

→ Aucune entrée ne montre **László Kramer 1903** né **fils de Zsigmond × Beck Sarolta**. L'acte civil de naissance 20.4.1903 Bp **n'est pas indexé** dans la portion publiée de Hungary CR aujourd'hui.

## Hypothèse

L'index FS pour Bp 1903 birthRegisters est **partiel**. Notre Mária Kramer née 14.12.1898 Bp VII. (Erzsébetváros) est indexée (ARK `3:1:S3HY-DTHW-8L`, Image Group 004403180), mais László né 5 ans plus tard 20.4.1903 ne l'est pas.

## Voie alternative — browse direct DGS

Pour récupérer l'acte naissance László 20.4.1903 :
1. Identifier le DGS BFL Bp Births 1903 (district VII. ou autre)
2. Browse images directement : `https://www.familysearch.org/search/film/<DGS>?i=<image>`
3. Localiser le folyószám ~20 avril 1903

Image Group estimés (Mária 1898 = `004403180`) :
- Bp VII. Births 1903 : DGS probable autour de `00440317x` ou plus tard si VII. continu, ou autre district
- À browse via le catalogue FS section *Hungary, Civil Registration → Budapest → kerület → Births 1903*

## Action différée

Récupération acte naissance László 20.4.1903 = browse manuel DGS — non priorisé dans cette session.

## Mise à jour mémoire

Ajout au feedback `feedback_familysearch_ui_vs_url.md` : **URL bricolée fonctionne SI** :
- elle est scopée à une collection précise (`f.collectionId=*`) OU
- les paramètres viennent de l'URL générée par FS lui-même (post-formulaire UI)
