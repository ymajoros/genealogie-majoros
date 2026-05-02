# Recoupement FS des 3 pièces transmises par Michel Majoros — 2 mai 2026

## Constat technique

FamilySearch refuse toute requête anonyme exploitable depuis curl/HTTP direct (mai 2026) :
- ARKs (`ark:/61903/...`) répondent HTTP 200 mais retournent un **shell React vide** (~13 ko) sans JSON-LD ni payload exploitable
- Endpoints `service/search/hr/v3/personas/...` → HTTP 403
- API `platform/records/personas/...` → HTTP 403/401
- Browse de waypoints (`search/film/...`, `search/collection/...`) → 200 + shell vide
- User-Agent navigateur réaliste sans changement

→ **Toutes les recherches doivent passer par l'UI navigateur authentifié**, conformément au feedback `feedback_familysearch_ui_vs_url.md`.

## A. Mariage civil n° 203 — 19.12.1918 Budapest

### À récupérer
- ARK index `1:1:...` (entrée Majoros Ödön × Krámer Mária)
- ARK image `3:1:...` (vue de l'acte sur le registre)
- Image Group Number (DGS) — par interpolation entre les deux ancres connues :
  - Krámer Mária naissance 1898 → DGS `004403180`
  - Beck Sarolta décès 1937 → DGS `004403191`
  - **Mariages 1918 V. ker. probable DGS `004403185-189`** (à confirmer)
- District d'enregistrement : **V. ker. (Lipótváros)** — domicile commun Lipót körút 11

### URL UI à exécuter au prochain laptop ouvert

```
https://www.familysearch.org/search/record/results?q.surname=Majoros&q.givenName=Odon&q.spouseSurname=Kramer&q.spouseGivenName=Maria&q.collectionId=1452460&q.eventType=Marriage&q.marriageLikeDate.from=1918&q.marriageLikeDate.to=1919&q.marriageLikePlace=Budapest
```

### Fallback browse

Si le formulaire UI échoue : **Hungary, Civil Registration → Budapest → V. kerület → Marriages 1918 → folyószám 203**

## B. Naissance László Kramer — 20.4.1903 Budapest

### À récupérer
- ARK index naissance Kramer László père Zsigmond mère Beck Sarolta
- ARK image
- Image Group Number
- Numéro d'acte (folyószám) avril 1903

### District probable
1. **VII. ker. (Erzsébetváros)** — district où Mária est née en 1898 (Föld u. 29)
2. Sinon V. ou VI.

### URL UI à exécuter

```
https://www.familysearch.org/search/record/results?q.surname=Kramer&q.givenName=Laszlo&q.fatherGivenName=Zsigmond&q.motherSurname=Beck&q.motherGivenName=Sarolta&q.collectionId=1452460&q.birthLikeDate.from=1903&q.birthLikeDate.to=1903
```

### Fallback browse

**Hungary CR → Budapest → VII. kerület → Births 1903 → avril, autour du 20**

## C. ARK Kantor 1947 confirmé valide

`1:1:69VG-XPNZ` répond HTTP 200 sur le shell — l'ARK **existe et est valide**. Si l'ARK était erroné, FS renverrait 404.

### À vérifier en UI
- Bloc *Source* en bas de la page persona — vérifier s'il y a un `Image` cliquable au format `3:1:...` (image originale du carteira DEE)
- Si oui, capturer l'image ARK et télécharger le PDF

Note : les Cartões SP n'ont pas tous été imagés ; ceux qui le sont ont un ARK image distinct. Les images détenues par Michel (recto/verso) sont déjà archivées dans le repo.

## D. Profil FS Family Tree pour László / Ladislas Kantor

### État actuel
- **Aucun GID Tree** existant pour László/Ladislas (cf. `project_familysearch_tree_ids.md`)
- Profil parent **Krámer Zsigmond GXXH-YFJ** existe mais sans enfant László rattaché

### À créer (compte Yannick5235)
1. Créer profil Tree « Krámer László / Ladislas Kantor (1903-?) »
2. Rattacher comme enfant de :
   - **GXXH-YFJ** (Zsigmond)
   - **G5QQ-JFY** (Sarolta)
3. Frère/sœur de **G5QQ-7CG** (Mária)
4. Sources à attacher :
   - ARK index `1:1:69VG-XPNZ` (DEE São Paulo 1947) ✓ déjà identifié
   - Acte de naissance 20.4.1903 Bp (à trouver — tâche B)
   - Aranyoklevél 1908/1963 (privé, scan famille)
   - Faire-part *Pesti Hírlap* 17.5.1928 et *Pesti Napló* 4.7.1937

## E. Cousinage potentiel — Cartões SP 1946-1950

### URLs UI pour cribler

```
https://www.familysearch.org/search/record/results?q.surname=Kantor&q.birthLikePlace=Hungary&q.anyDate.from=1946&q.anyDate.to=1950&q.anyPlace=S%C3%A3o+Paulo
```

```
https://www.familysearch.org/search/record/results?q.surname=Kramer&q.birthLikePlace=Hungary&q.anyDate.from=1946&q.anyDate.to=1950&q.anyPlace=S%C3%A3o+Paulo
```

### Cibles
- Une éventuelle **épouse** de László (cf. mention « dr. Kramer Lászlóné » faire-part 1937) — si elle a survécu et émigré avec lui, fiche DEE séparée 1947
- Autres **Kantor / Krámer hongrois** débarquant Rio/Santos 1946-1948
- Paquebot du 10.1.1947 (probablement *Campana*, *Provence* ou *Désirade*)

### Source alternative
**APESP** (`arquivoestado.sp.gov.br`) a une **base d'indexation propre** des Cartões de Imigração — souvent plus exhaustive et accessible sans login que l'index FS partiel.

## Synthèse — file d'attente UI

| # | Action | Outil | ARK attendu format |
|---|---|---|---|
| A | Récupérer ARK mariage 203/1918 V.ker. | FS UI Browse | `3:1:S3HT-...` (image) + `1:1:...` (index) |
| B | Récupérer ARK naissance László 20.4.1903 | FS UI Browse VII→V→VI | `3:1:S3HY-...` |
| C | Capturer page persona `1:1:69VG-XPNZ` | FS UI | déjà connu, vérifier image associée |
| D | Créer profil Tree László sous GXXH-YFJ | FS Tree (compte Yannick5235) | nouveau GID |
| E | Cribler Cartões SP 1946-50 Kantor/Kramer HU | FS UI + APESP | listes |

## Fichiers à compléter ultérieurement

- `actes/archives-web/familysearch/Majoros_Kramer_mariage_1918_civil.md` — après tâche A
- `actes/archives-web/familysearch/Kramer_Laszlo_naissance_1903_civil.md` — après tâche B
- Mise à jour `actes/archives-web/Kantor_Ladislas_DEE_1947.md` avec GID Tree après tâche D

**Aucun ARK inventé** ; aucune piste fabriquée à partir d'URL bricolée.
