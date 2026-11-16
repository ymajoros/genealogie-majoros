# Handover : session du 4 novembre 2026 (police politique hongroise, Ferenc Majoros)

## Demande initiale
Le 4.11.2026, la Hongrie a ouvert **nyitottaktak.hu**, la base ÁBTL des « personnes de réseau » (informateurs) de 1945 à 1990. Objectif : vérifier si des membres de la famille du repo `genealogie-majoros` y figurent, puis rassembler le maximum d'informations sur **Ferenc Imre Majoros** (1923-2008), grand-père de Yannick (confirmé par lui).

## Livrables produits (à commiter, la session n'a pas les droits de push)
- `docs/notes-recherche/ferenc-majoros-1948-1963-defection-2026-11-04.md` : note de recherche complète (sources, statuts [✓]/[◐]/[?], pistes)
- `actes/archives-web/hungaricana/MNL_OL_XIX-A-83-b_3304-1963_delegation_Tokyo_Majoros_Ferenc.jpg` : capture de la décision gouvernementale 3304/1963
- ce fichier

## Résultats clés
1. **Aucun membre identifié de la famille n'apparaît comme informateur** sur nyitottaktak.hu. Recherches faites : Majoros (52 résultats, aucun avec pour mère Kramer/Krámer/Heiduska), Majoros Ferenc 1920-26, Majoros Gábor 1950-52, Majoros Mihály 1948-52, Kramer/Krámer, Smolsk, Smalst, Montag. Homonymes écartés par le nom de la mère.
2. **Entrée non attribuable** : « Majoros Ferencné », registre B, dossier **B-97156**, ligne 156 « meghiúsult » (recrutement avorté), d'après la fiche 6 de « Gy. Szűcs László ». Pas de date de naissance ni de nom de mère. Ne rien conclure.
3. **Carrière de Ferenc en Hongrie** (décisions du Conseil des ministres, MNL OL XIX-A-83-b, via Hungaricana) : 1959, accord aérien Hongrie-Autriche ; 1961, conférence de droit aérien au Mexique (Guadalajara) ; **août 1963**, délégué à la conférence ICAO de Tokyo (décision 3304/1963). Son titre : *jogtanácsos* (conseiller juridique) de la KPM Légügyi Főigazgatóság. Une mention de 1948 (nomination, Sofia ?) reste à relire.
4. **Défection** : Pál István, *Szakmai Szemle* (KNBSZ) 2024/3-4, p. 11, écrit qu'il « n'est pas rentré de Londres à l'automne 1963 ». Il cite le dossier ÁBTL « Medúza » 3.2.5 O-8-016/3/2 (rapport du 10.12.1963, p. 35-57). Le titre de poste identique et la chronologie rendent l'identification **très probable**. Dans ces archives, il est une **cible**, rien n'indique qu'il ait été informateur.
5. **Correction pour le README** : la date « ab 1962 » de Wikipédia DE est probablement fausse. L'arrivée en RFA est à placer fin 1963 ou plus tard, après Londres. Le §5 du README est à mettre à jour.

## Questions de Yannick traitées
- « Quel historien le cite ? Michel ? » → Non : István Pál (article sur la perception britannique de l'ÁVH, rapport de l'ambassadeur Richard Parsons).

## Pistes ouvertes (par priorité)
1. **ÁBTL, demande de consultation** (portail https://lar.abtl.hu/ords/r/abtl/sb/home, option famille décédée ; sans Ügyfélkapu, envoi postal signé ; pièces d'état civil pour la filiation Yannick → Michel → Ferenc). Demander nommément le dossier « Medúza » et les dossiers O/V/M ouverts sur Ferenc après 1963, ainsi que ceux de la période Varsovie 1948-49. Délai : 7-8 mois ou plus.
2. Relire la page 226 de G. Vass, *Minisztertanácsi jegyzőkönyvek napirendi jegyzékei 1947-1950* (Hungaricana `MolDigiLib_MOLsegedl_11_2`), pour la nomination de 1948. Le viewer s'est figé pendant la session.
3. Bundesarchiv : procédure d'accueil des réfugiés (Notaufnahme) ou dossier du Bundesamt de Zirndorf, pour la date d'arrivée en RFA ; archives du BIOst Köln (dissous en 2000, où il a publié).
4. The National Archives (Kew) : FOI sur un transfuge hongrois à l'automne 1963.
5. ICAO : listes de délégués de Tokyo (1963) et de Guadalajara (1961).
6. Universitätsarchiv Köln (IPR-Institut, 1967-1988) ; *Die Friedens-Warte* vol. 83 (2008), nécrologie éventuelle.
7. Revenir sur nyitottaktak.hu : les dossiers B sont mis en ligne progressivement jusqu'au 25.2.2027.

## Notes techniques pour la prochaine session
- nyitottaktak.hu est une application dynamique : WebFetch ne passe pas, il faut passer par Chrome. Chrome traduit automatiquement les pages, ce qui fausse les noms : lire le texte brut. Une boucle JS qui remplit les champs (`placeholder` Name / Mother's name / -from / until) puis clique sur `button[type=submit]` permet d'enchaîner les requêtes.
- Le PDF KNBSZ est refusé par WebFetch (robots) et par curl (certificat SSL). Il est accessible via la copie du numéro complet sur Azure blob (URL dans le rapport de recherche).
- La DNB (portal.dnb.de) bloque WebFetch (Anubis) mais passe dans Chrome.
- La *Bibliography of Hungarian legal literature 1945-1980* (Nagy Lajos) a été consultée : rien sur Majoros. Elle ne recense que les publications en langues étrangères.
