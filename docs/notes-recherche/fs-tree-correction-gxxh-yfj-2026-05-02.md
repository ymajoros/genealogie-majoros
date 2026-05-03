# FS Tree GXXH-YFJ — corrections nécessaires (audit 2 mai 2026)

## Constat

URL : <https://www.familysearch.org/tree/person/details/GXXH-YFJ>

État aujourd'hui (2 mai 2026, après modifications de Katalin Demeter le 11 mars 2024) :

| Champ | Valeur sur FS Tree | État correct |
|---|---|---|
| **Name** | **Simon Kramer** ❌ | **Zsigmond Krámer** (Krámer Zsigmond en hongrois) |
| Sex | Male | ✓ |
| Death | « Deceased » (sans date) | †16 mai 1928 Bp Kozma (cf. *Pesti Hírlap* 17.5.1928 + acte civil 1928 ARK `1:1:6TFN-D6MW`) |
| Spouse | **Sarolta Beck** G5QQ-JFY (1873-1937) | ✓ |
| Marriage Events | « No Marriage Events » | À ajouter : ~1893-1897 Budapest ou Komárom |
| Children | Mária Kramer 1898 GSQQ-7CG ✓ | ✓ Mária correcte |
| Children | **Lea Krámer 1902 GXXH-TDT** ❌ | **À DÉTACHER** — pas notre famille (audit 25.4.2026) |
| Missing child | (absent) | **László Krámer 1903 GXXH-YFJ-?** ⭐ — à créer/attacher |
| Father | (absent) | À ajouter : **Krámer Ármin/Hermán** (b ~1830-1845, †≤1928 Ujlak ; cf. acte civil décès 1928) |
| Mother | (absent) | À ajouter : **Brunn (Braun) Jozefa** (b 1840 d 10.11.1925 Bp Kozma id 91876) |
| Siblings | (absents) | 6 frères/sœurs documentés via FS Hungary Jewish VR Index (Netti, Regi, Sali, Julie, Isák, Adolf — cf. README §3.1) |

## Source de l'erreur de nommage

Hypothèse : la **« Simon Kramer »** vient de l'acte de mariage 1936 Lea Kramer × Goldstein Jenő, où le père de Lea est lu **« Simon Kramer »** ; **mais** la mère sur cet acte est **Keimovits Sarolta**, PAS Beck Sarolta — donc le « Simon Kramer » de l'acte 1936 = père de Lea, **pas notre Zsigmond** (cf. audit Lea Kramer `docs/pistes-fermees/lea-kramer-goldstein-mauvais-rattachement/`).

L'utilisateur antérieur **XXY29** (et plus récemment Katalin Demeter) a confondu deux personnes différentes :
- **Zsigmond/Sigismund/Sigismundo Krámer** (notre ancêtre) × Beck Sarolta → enfants Mária 1898 + László 1903
- **Simon Krámer** (sans lien) × Keimovits Sarolta → enfant Lea 1902

Le profil GXXH-YFJ a été créé avec le NOM erroné « Simon Kramer » mais avec la BONNE épouse (Beck Sarolta) et la BONNE fille (Mária 1898). Puis Lea a été attachée à tort.

## Corrections recommandées (à exécuter par Yannick sur son compte FS)

1. **Renommer GXXH-YFJ** en **Zsigmond Krámer** (ou Krámer Zsigmond) avec sources :
   - Acte civil décès 1928 ARK [`1:1:6TFN-D6MW`](https://www.familysearch.org/ark:/61903/1:1:6TFN-D6MW) (image `S3HT-D553-567`)
   - Faire-part *Pesti Hírlap* 17.5.1928
   - Magyarisation patronymique : ce n'est pas un Simon, c'est bien un Zsigmond
2. **Ajouter date décès** : 16 mai 1928 Budapest, sépulture Kozma utca parc.15 sor.31 sir.20
3. **Ajouter date naissance** : 24 décembre 1871 Ujlak, Nyitra (acte FS index `1:1:6DS2-Y632`, image `3:1:9398-9T96-SG`)
4. **Détacher Lea Krámer GXXH-TDT** (relationship to delete) — pas fille de Zsigmond × Beck Sarolta
5. **Créer profil László Krámer (1903-?)** :
   - Naissance 20 avril 1903 (probablement Bp VII, à confirmer)
   - Décès São Paulo, date à établir
   - Émigré Brésil 1947 sous le nom **Ladislas Kantor**
   - Marié 16 décembre 1933 Budapest avec **Bokor Panni** (= probable Anna Bokor née Elek, Yad Vashem item 5019833, *murdered Shoah*)
   - Sources : fiche DEE São Paulo n° 226607 du 02.04.1947 + Hungaricana ADT (carrière vegyészmérnök, brevet 95816, cégvezető Klein és Fia)
6. **Ajouter parents** Krámer Ármin × Brunn Jozefa
7. **Ajouter mariage** Sarolta Beck (date à confirmer)

## Action sur FS

Toutes ces actions sont des **edits du FS Family Tree** — à exécuter sur le compte personnel Yannick5235. La session UI actuelle ne les fait PAS pour éviter de modifier le compte de l'utilisateur sans son contrôle.

Voir aussi mémoire `project_familysearch_tree_ids.md` à mettre à jour : GXXH-YFJ « Zsigmond Krámer » (pas « Simon Kramer »).

## Recherche ARK Kantor 1947

URL `1:1:69VG-XPNZ` retourne 404 aujourd'hui. Recherches dans collection FS *Brazil, São Paulo, Cartões de Imigração 1902-1980* (id 2140223) avec critères :
- Surname Kantor + birth 1903 → 0 résultats
- Father « Sigismundo Kramer » + Mother « Charlotte Beck » → 0 résultats
- Father « Zsigmond Kramer » + Mother surname Beck → 0 résultats
- Birth Hungary 1903 → 0 résultats

→ **Le record Kantor 1947 n'est PAS dans la portion publiée de l'index FS aujourd'hui**. La collection 2140223 indexe « Some of these records » seulement. Le record était indexé en mars 2026 (screenshot Michel) mais a été dé-indexé/réindexé entre-temps.

**Voies pour récupérer le bon ARK** :
1. Contacter le support FS (`https://www.familysearch.org/contact`) en citant l'ancien ARK 69VG-XPNZ + le ID Item 226607 + le screenshot Michel
2. APESP (Arquivo Público do Estado de São Paulo) accès direct à la fiche d'origine
3. Browse direct des images de la collection : `https://www.familysearch.org/search/film/<DGS>` une fois le DGS Cartões 1947 identifié (à chercher via Catalog → Brazil → São Paulo)
4. Reconnu : la screenshot familiale Michel reste la preuve primaire, l'ARK FS étant secondaire

## Synthèse

| Action | Statut | Priorité |
|---|---|---|
| Renommer GXXH-YFJ en Zsigmond | À faire | Haute |
| Détacher Lea GXXH-TDT | À faire | Haute |
| Créer profil László Kramer 1903 | À faire | Haute |
| Trouver nouvel ARK Kantor 1947 | Inconcluant via UI | Reporter (support FS / APESP) |
| Ajouter parents Ármin × Jozefa | À faire | Moyenne |
| Documenter dans README | ✓ ce document | Fait |
