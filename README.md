# 🎮 NIVEAU 1 – Série TikTok

Série TikTok d'action absurde en **pixel art 16-bit rétro**. Un héros de niveau 1, **Gaston**, voyage dans de **vraies villes à de vraies époques** et y vit des anecdotes historiques *très* enjolivées, qui se terminent par un combat de boss et une petite morale.

> *« Inspiré de faits réels. Enfin… à peu près. »*

## Les règles de la série
- **Accroche, identique à chaque épisode :** « 💾 Chargement de la sauvegarde… Année [XXXX]. Lieu : [Ville]. »
- **Outro, identique à chaque épisode :** « 🏆 Quête terminée. Leçon obtenue : [morale]. Gaston passe au niveau [X]. »
- **Durée :** 60 à 90 s, au format 9:16 (au moins 1 min pour être éligible au Creator Rewards Program).
- **Rythme :** une coupe ou un mouvement toutes les 2 à 3 s, trois escalades, un boss, une fausse victoire, une chute.
- **Running gag :** Bernard, le PNJ blasé, a le même visage à chaque époque, seul son costume change.
- **Originalité :** aucun personnage, logo ou musique d'une œuvre existante. Label « contenu IA » activé sur TikTok.

## Comment utiliser ce dépôt (dans l'ordre)
1. `00_methode_kling.md` : la méthode de production sur Kling AI (résumé).
   👉 **`02_guide_kling_pas_a_pas.md` : le guide détaillé, des images à la vidéo finale.**
2. `01_style_global.md` : le bloc **STYLE** et le **prompt négatif**, à coller partout.
3. `personnages/` : génère les fiches des personnages et garde les meilleures comme références.
4. `decors/` : génère les décors de l'épisode.
5. `episodes/<épisode>/script.md` : lis le script.
6. `episodes/<épisode>/plans_kling.md` : génère les plans un par un (image de départ, puis animation).
7. `montage/` : ajoute l'interface, les textes et les sons, puis vérifie la checklist avant de publier.

## Structure
```
├── 00_methode_kling.md
├── 01_style_global.md
├── 02_guide_kling_pas_a_pas.md
├── personnages/            gaston.md, bernard.md, figurants par épisode
├── decors/                 décors par épisode + écrans récurrents
├── episodes/
│   └── episode01_strasbourg_1518/
│       ├── script.md
│       └── plans_kling.md
└── montage/                interface_ui.md, checklist.md
```

## Épisodes
| # | Titre | Lieu / époque | Boss | Leçon |
|---|---|---|---|---|
| 01 | La Danse Maudite | Strasbourg, 1518 | Le Ménestrel Maudit | Parfois, au lieu de lutter contre le courant… danse avec. |

## Ajouter un épisode
1. Crée `episodes/episodeXX_ville_annee/` avec `script.md` et `plans_kling.md`.
2. Ajoute le nouveau costume de Bernard dans `personnages/bernard.md`.
3. Ajoute les nouveaux personnages dans `personnages/episodeXX_figurants.md` et les décors dans `decors/episodeXX_decors.md`.
4. Réutilise les écrans D4 (chargement) et D5 (fin) sans les modifier.
