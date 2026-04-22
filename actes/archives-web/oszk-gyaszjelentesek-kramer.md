# OSZK Gyászjelentések — recherche Kramer (index)

**Date de mise à jour** : 2026-04-22
**Statut** : dépouillement partiel effectué via Claude-in-Chrome — les faire-part pertinents sont **téléchargés et transcrits** dans [oszk-gyaszjelentesek/README.md](oszk-gyaszjelentesek/README.md).

---

## Note historique sur WebFetch

Les premiers essais de recherche via WebFetch sur cette base ont produit des résultats hallucinés (deux fetches successifs de la même entrée donnant des données contradictoires). Le problème a été contourné en inspectant les pages via Claude-in-Chrome et en téléchargeant directement les bitstreams officiels (`*_mormon.jpg` fac-similé + `*_work.txt` OCR). Cette méthode produit des données primaires vérifiables.

## Résultats consolidés

Voir le dossier détaillé [oszk-gyaszjelentesek/](oszk-gyaszjelentesek/) :

- **Kramer Ignácz 1881** — père des quatre frères, fratrie complète établie
- **Kramer Samu 1906** — frère non anobli (fabricant de meubles de cour impériale), faire-part qui cite explicitement les 3 frères anoblis avec prédicat *szinóbányai*
- 4 homonymes vérifiés et écartés

Le détail des trouvailles, des transcriptions et des implications généalogiques figure dans [oszk-gyaszjelentesek/README.md](oszk-gyaszjelentesek/README.md).

## URL stables

- Recherche générale : https://dspace.oszk.hu/handle/20.500.12346/663648/discover
- Parcours par date : https://dspace.oszk.hu/handle/20.500.12346/663648/browse?type=dateissued
- Parcours par titre (nom) : https://dspace.oszk.hu/handle/20.500.12346/663648/browse?type=title

## Pattern de téléchargement direct (à partir d'un handle)

```
https://dspace.oszk.hu/bitstream/handle/20.500.12346/{handleID}/{archiveFile}_mormon.jpg
https://dspace.oszk.hu/bitstream/handle/20.500.12346/{handleID}/{archiveFile}_work.txt
```

Où `{archiveFile}` a typiquement la forme `4311496_XXXXX` pour la collection Kramer.
