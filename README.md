# 🎮 NIVEAU 1 – Série TikTok

Série TikTok d'aventure absurde en **pixel art 16-bit rétro**, en vue POV et en 2 parties. **Bernard**, un PNJ cynique et génial qui sait qu'il vit dans un jeu, traîne de force **Sami**, joueur niveau 1 anxieux au grand cœur, dans de **vraies villes à de vraies époques**. Ils y vivent des anecdotes historiques *très* enjolivées : beaucoup d'humour, un vrai moment d'émotion par épisode, un vote du public, un combat de boss et une petite morale.

> *« Inspiré de faits réels. Enfin… à peu près. »*

## Les règles de la série
- **Accroche, identique à chaque épisode :** « 💾 Chargement de la sauvegarde… Année [XXXX]. Lieu : [Ville]. »
- **Outro, identique à chaque épisode :** « 🏆 Quête terminée. Leçon obtenue : [morale]. Sami passe au niveau [X]. »
- **Durée :** 60 à 90 s, au format 9:16 (au moins 1 min pour être éligible au Creator Rewards Program).
- **Rythme :** une coupe ou un mouvement toutes les 2 à 3 s, trois escalades, un boss, une fausse victoire, une chute.
- **Le duo :** Bernard (cynique, génial, « Spoiler : ça va mal finir ») et Sami (anxieux, sincère, « On va mourir. On va vraiment mourir. »). Bernard a le même visage à chaque époque, seul son costume change.
- **Ton :** humour accessible à tous + 1 moment sincère par épisode. Voir `04_ton_et_humour.md`.
- **Format :** partie 1 = cliffhanger + vote A/B en commentaire ; partie 2 = suite selon le vote + leçon + carte « 📜 FAIT RÉEL ».
- **Originalité :** aucun personnage, logo ou musique d'une œuvre existante. Label « contenu IA » activé sur TikTok.

## Comment utiliser ce dépôt (dans l'ordre)
1. `00_methode_kling.md` : la méthode de production sur Kling AI (résumé).
   👉 **`02_guide_kling_pas_a_pas.md` : le guide détaillé, des images à la vidéo finale.**
   🆕 **`03_format_pov_interactif.md` : le nouveau format POV interactif en 2 parties + épisode 1 réécrit.**
   🎭 **`04_ton_et_humour.md` : le duo Bernard / Sami, les types d'humour, le dosage drame/humour, les voix.**
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
├── 03_format_pov_interactif.md
├── 04_ton_et_humour.md
├── personnages/            sami.md, bernard.md, figurants par épisode
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
