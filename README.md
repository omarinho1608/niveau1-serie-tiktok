# 🎮 NIVEAU 1 – Série TikTok

Série TikTok d'aventure absurde en **pixel art 16-bit rétro**, en vue POV et en 2 parties. **Bernard**, un PNJ cynique et génial qui sait qu'il vit dans un jeu, traîne de force **Sami**, joueur niveau 1 anxieux au grand cœur, dans de **vraies villes à de vraies époques**. Ils y vivent des anecdotes historiques *très* enjolivées : beaucoup d'humour, un vrai moment d'émotion par épisode, un vote du public, un combat de boss et une petite morale.

> *« Inspiré de faits réels. Enfin… à peu près. »*

## Les règles de la série
- **Accroche, identique à chaque épisode :** « 💾 Chargement de la sauvegarde… Année [XXXX]. Lieu : [Ville]. »
- **Outro, identique à chaque épisode :** « 🏆 Quête terminée. Leçon obtenue : [morale]. Sami passe au niveau [X]. »
- **Durée :** 60 à 90 s, au format 9:16 (au moins 1 min pour être éligible au Creator Rewards Program).
- **Rythme :** une coupe ou un mouvement toutes les 2 à 3 s, trois escalades, un boss, une fausse victoire, une chute.
- **Le duo :** Bernard (cynique, génial, « Spoiler : ça va mal finir ») et Sami (anxieux, sincère, « On va mourir. On va vraiment mourir. »). Bernard a le même visage à chaque époque, seul son costume change.
- **Ton :** humour accessible à tous + 1 moment sincère par épisode. Voir `docs/3_ton_et_humour.md`.
- **Format :** partie 1 = cliffhanger + vote A/B en commentaire ; partie 2 = suite selon le vote + leçon + carte « 📜 FAIT RÉEL ».
- **Originalité :** aucun personnage, logo ou musique d'une œuvre existante. Label « contenu IA » activé sur TikTok.

## 👉 Tu cherches quoi ?
| Je veux… | Va dans |
|---|---|
| **Générer les nouvelles scènes de l'épisode 1** | 📁 [`episodes/ep01_strasbourg_1518/A_GENERER_kling/`](episodes/ep01_strasbourg_1518/A_GENERER_kling/) |
| Lire le script de la partie 1 | [`episodes/ep01_strasbourg_1518/1_partie1_script.md`](episodes/ep01_strasbourg_1518/1_partie1_script.md) |
| Savoir quel clip va où au montage | [`episodes/ep01_strasbourg_1518/3_montage_partie1.md`](episodes/ep01_strasbourg_1518/3_montage_partie1.md) |
| Comprendre comment utiliser Kling | [`docs/1_guide_kling_pas_a_pas.md`](docs/1_guide_kling_pas_a_pas.md) |
| Le bloc de style et le prompt négatif | [`docs/2_style_global.md`](docs/2_style_global.md) |
| Le ton, l'humour, le duo Bernard / Sami | [`docs/3_ton_et_humour.md`](docs/3_ton_et_humour.md) |
| Le format POV interactif en 2 parties | [`docs/4_format_pov_interactif.md`](docs/4_format_pov_interactif.md) |
| Les fiches des personnages | [`personnages/`](personnages/) |
| Les décors | [`decors/`](decors/) |
| L'interface de montage et la checklist | [`montage/`](montage/) |

## Structure
```
niveau1-serie-tiktok/
├── README.md                         ← tu es ici
├── docs/                             ← les règles de la série (communes à tous les épisodes)
│   ├── 1_guide_kling_pas_a_pas.md
│   ├── 2_style_global.md
│   ├── 3_ton_et_humour.md
│   └── 4_format_pov_interactif.md
├── personnages/
│   ├── sami.md
│   ├── bernard.md
│   └── ep01_personnages.md           ← Maire, Ménestrel, Greta, Frau Troffea, figurants
├── decors/
│   └── ep01_decors.md
├── episodes/
│   └── ep01_strasbourg_1518/
│       ├── 1_partie1_script.md
│       ├── 2_partie2_a_ecrire.md
│       ├── 3_montage_partie1.md      ← quel clip pour quel plan
│       ├── A_GENERER_kling/          ← 🎬 LES SCÈNES À FAIRE (1 fichier = 1 scène)
│       └── archive_v1/               ← ancien script et anciens prompts (tes clips déjà générés)
└── montage/
    ├── interface_ui.md
    └── checklist.md
```

## Épisodes
| # | Titre | Lieu / époque | Boss | Leçon |
|---|---|---|---|---|
| 01 | La Danse Maudite | Strasbourg, 1518 | Le Ménestrel Maudit | Parfois, au lieu de lutter contre le courant… danse avec. |

## Ajouter un épisode
1. Crée `episodes/epXX_ville_annee/` sur le modèle de `ep01` : `1_partie1_script.md`, `2_partie2…`, `3_montage_partie1.md` et un dossier `A_GENERER_kling/` (1 fichier = 1 scène, prompts complets).
2. Ajoute le nouveau costume de Bernard dans `personnages/bernard.md`.
3. Ajoute les nouveaux personnages dans `personnages/epXX_personnages.md` et les décors dans `decors/epXX_decors.md`.
4. Réutilise les écrans D4 (chargement) et D5 (fin) sans les modifier.
