# Guide pas à pas : des images à la vidéo finale avec Kling

> Les noms des boutons peuvent varier selon ta version de Kling (3.0, Omni…). Si un nom ne correspond pas exactement, cherche la fonction équivalente.

## Vue d'ensemble

```
Images des persos + images des décors
        │
        ▼
ÉTAPE 1 : créer un « Element » par personnage (bibliothèque Kling)
        │
        ▼
ÉTAPE 2 : fabriquer l'IMAGE CLÉ de chaque plan (perso + décor dans une même image)
        │
        ▼
ÉTAPE 3 : animer chaque image clé (Image-to-Video + perso lié)
        │
        ▼
ÉTAPE 4 : voix · ÉTAPE 5 : montage CapCut · ÉTAPE 6 : publication
```

**L'idée clé :** Kling n'anime pas « un perso + un décor » séparés. Il anime **une seule image de départ** dans laquelle le personnage est **déjà placé** dans le décor. Cette image s'appelle l'**image clé** (keyframe). Tout le travail consiste à fabriquer une bonne image clé par plan.

---

## ÉTAPE 0 : Organiser tes fichiers (5 min)

Crée ces dossiers sur ton ordinateur :
```
Niveau1_Ep01/
├── 1_refs_persos/     sami_face.png, sami_profil.png, bernard_face.png…
├── 2_refs_decors/     D1_place.png, D2_balcon.png, D3_parvis.png, D4.png, D5.png
├── 3_images_cles/     plan01.png, plan02.png … plan25.png
├── 4_clips/           plan01.mp4, plan02.mp4 …
├── 5_voix/            sami_01.mp3, bernard_01.mp3 …
└── 6_sons_musique/
```
Nomme toujours les fichiers par numéro de plan. Au montage, c'est ce qui te fera gagner le plus de temps.

---

## ÉTAPE 1 : Créer les Elements (une seule fois pour toute la série)

Un **Element**, c'est une « carte d'identité » du personnage que Kling garde en mémoire. Tu le crées une fois et tu le réutilises dans tous les plans et tous les épisodes.

1. Ouvre la **bibliothèque d'Elements** (*Element Library*).
2. Crée un nouvel Element de type **personnage**.
3. Choisis l'**image principale** : le personnage **de face**, en entier, sur fond uni. C'est la plus importante.
4. Ajoute **1 à 3 images supplémentaires** : profil, dos, une expression. Kling accepte 2 à 4 images en tout.
5. Donne-lui un nom simple : `Sami`, `Bernard`, `Maire`, `Menestrel`.

À créer :
| Element | Image principale | Images supplémentaires |
|---|---|---|
| Sami | face | profil, dos, visage « choqué » |
| Bernard (moine) | face | profil, portrait visage |
| Maire | face | profil |
| Menestrel | face | profil |

> Les **foules** (danseurs, musiciens) ne sont **pas** des Elements. Tu les décris dans le prompt (fiche ADN) : elles n'ont pas besoin d'être identiques d'un plan à l'autre.

> Si tes images de référence ont un décor chargé, détoure-les d'abord (CapCut, Canva ou remove.bg) : un fond uni donne des Elements bien plus fiables.

---

## ÉTAPE 2 : Fabriquer l'image clé de chaque plan

C'est l'étape qui te bloquait. Il y a deux méthodes. Commence par la A, et passe à la B si le résultat ne te plaît pas.

### Méthode A : Composition par Kling (génération d'image avec références)

1. Va dans la **génération d'image** de Kling, en mode « avec image(s) de référence » (Omni / référence, selon ta version).
2. Ajoute l'**image du décor** du plan (voir le tableau plus bas).
3. Ajoute l'**Element** ou les Elements du ou des personnages du plan (3 maximum).
4. Format **9:16**.
5. Colle ce modèle de prompt en remplaçant les crochets :

```
Use the background image as the exact scene and keep its style and composition.
Place [Sami] in this scene: [action / pose / expression du plan, reprise du prompt KEYFRAME].
Characters must keep exactly their reference design, proportions and colors.
Same 16-bit retro pixel art style as the background, crisp clean pixels, thick dark outlines, flat vibrant colors, vertical 9:16.
```
6. Génère 4 versions et garde la meilleure dans `3_images_cles/planXX.png`.

**Vérifie avant de passer à la suite :**
- [ ] Le perso ressemble à sa référence (casque, écharpe, bottes dépareillées…).
- [ ] Il est à la **bonne taille** par rapport au décor.
- [ ] Le style pixel est **identique** entre le perso et le décor : pas de perso lisse sur un décor pixel.
- [ ] Il reste de la place pour l'action : le perso n'est pas collé au bord si le plan prévoit qu'il court.

### Méthode B : Collage manuel, puis harmonisation (la plus fiable)

1. Dans **Canva / CapCut / Photopea** (gratuit), ouvre le décor en 1080×1920.
2. Colle le perso **détouré** (PNG sans fond) par-dessus, place-le et mets-le à la bonne taille.
3. Exporte en PNG.
4. *(Optionnel)* Repasse l'image dans la génération d'image Kling avec la consigne : `Keep everything exactly the same, only harmonize lighting and pixel style so the character blends naturally into the background.`
5. Ce collage devient ton image clé.

### Plans sans personnage, ou réutilisés
- **Plans 01, 14, 25 :** le décor (D4, D3, D5) sert directement d'image clé.
- **Plan 04 :** réutilise l'image clé du plan 03.
- **Plan 18 :** réutilise l'image clé du plan 17.
- **Plan 19 :** gros plan du visage de Sami sur fond violet. Pas besoin de décor : génère-le avec l'Element Sami seul.

### Tableau : quel décor et quels persos pour chaque plan

| Plan | Décor | Elements à lier | Foule à décrire dans le prompt |
|---|---|---|---|
| 01 | D4 | — | — |
| 02 | D1 (vue du ciel) | Sami | — |
| 03 | D1 | Sami | danseurs |
| 04 | = image du plan 03 | Sami | danseurs |
| 05 | D1 (flou en fond) | Bernard | danseurs |
| 06 | D1 | Sami + Bernard | — |
| 07 | **Rue** (décor à créer, voir plus bas) | Sami | danseurs |
| 08 | **Rue** (vue de côté) | Sami | 1 danseur + charrette |
| 09 | D1 | Sami | 1 danseur |
| 10 | D1 | Sami | danseurs |
| 11 | D2 | Maire | — |
| 12 | D1 | — | musiciens + danseurs |
| 13 | D1 | — | danseurs + musiciens |
| 14 | D3 | — | — |
| 15 | D3 | Menestrel + Sami | — |
| 16 | D3 | Menestrel + Sami | — |
| 17 | D3 | Sami + Menestrel | — |
| 18 | = image du plan 17 | Sami + Menestrel | — |
| 19 | fond violet uni | Sami | — |
| 20 | D3 | Sami + Menestrel | — |
| 21 | D3 | Sami + Menestrel | — |
| 22 | D1 | — | danseurs + musiciens au sol |
| 23 | D1 (sol pavé, vue du dessus) | Bernard | — |
| 24 | D2 | Maire | — |
| 25 | D5 | — | — |

**Décor manquant pour les plans 07 et 08 (la rue) :**
```
Narrow medieval street in Strasbourg in 1518, half-timbered houses with red roofs on both sides, cobblestones, a wooden hay cart, bright sunny day, no characters. 16-bit retro pixel art, crisp clean pixels, thick dark outlines, flat vibrant colors, classic retro adventure game aesthetic, high quality pixel environment, vertical 9:16 composition
```
Pour le plan 08, ajoute `side view like a retro platform game` au prompt.

---

## ÉTAPE 3 : Animer chaque image clé (Image-to-Video)

Pour **chaque plan**, dans l'ordre :

1. Va dans **Vidéo → Image-to-Video**.
2. **Image de départ** (*start frame*) : charge `3_images_cles/planXX.png`.
3. **Lier les personnages** : active l'option de liaison des sujets (*Bind Subject / Enhance Consistency*) et sélectionne les Elements présents **dans l'image** (3 maximum). Ça empêche le visage et le costume de se déformer pendant le mouvement.
4. **Prompt** : colle le prompt **MOTION** du plan (fichier `plans_kling.md`) et ajoute à la fin :
   `pixel art style preserved, characters keep their exact design`
5. **Prompt négatif** : colle celui de `01_style_global.md`.
6. **Réglages** :
   - format **9:16** ;
   - durée **5 s** (10 s seulement pour le plan 20) ;
   - curseur **Creativity / Relevance** poussé vers **Relevance** ;
   - mode qualité le plus élevé disponible.
7. Lance **2 à 4 générations** et garde la meilleure dans `4_clips/planXX.mp4`.

### Quand utiliser l'image de FIN (*end frame*)
Ajoute une image de fin quand le plan doit **finir précisément** d'une certaine manière :
- **Plan 04** : début = plan 03, fin = Sami aplati au sol.
- **Plan 21** : début = Sami attrape le câble, fin = câble arraché, plus de lueur violette.
- **Plan 22** : début = tout le monde debout figé, fin = tout le monde au sol.

Pour créer l'image de fin, refais l'Étape 2 avec la pose finale.

### Si ça rate (problèmes fréquents)
| Problème | Solution |
|---|---|
| Le pixel art devient lisse ou « 3D » | Pousse le curseur vers Relevance, ajoute `no smoothing, no 3D` au négatif, demande moins de mouvement |
| Le perso change de visage | Vérifie que l'Element est bien lié, raccourcis l'action, et décris une seule action par plan |
| Trop de choses bougent | Ajoute `static background` dans le prompt |
| L'action ne se passe pas | Simplifie le prompt : sujet + verbe + direction (« Sami jumps to the right ») |
| La caméra fait n'importe quoi | Précise `static camera` ou un seul mouvement (`slow push-in`) |
| Le plan est trop chaotique (foules) | Accepte-le : 1 à 2 s de chaos suffisent, tu couperas au montage |

> **Astuce budget crédits :** fais d'abord **un test en qualité standard** sur 2 ou 3 plans difficiles (07, 13, 20) pour valider le style avant de tout générer en haute qualité.

---

## ÉTAPE 4 : Les voix

**Option 1 (recommandée) : ElevenLabs ou équivalent**
1. Choisis **une voix fixe par personnage** et note son nom :
   - Sami : jeune, énergique, sûr de lui ;
   - Bernard : grave, lent, monotone, fatigué ;
   - le Maire : pompeux, théâtral ;
   - le Ménestrel : grave, inquiétant, qui traîne sur les mots.
2. Génère chaque réplique séparément : `bernard_01.mp3`, `sami_02.mp3`…
3. Place-les au montage sur le bon plan.

**Option 2 : la voix dans Kling** (si ta version le permet)
Kling 3.0 Omni permet d'associer une voix à un Element personnage. C'est pratique pour synchroniser les lèvres, mais vérifie que la voix reste la même d'un plan à l'autre.

> En pixel art, une synchronisation labiale parfaite n'est pas nécessaire : une bouche qui s'ouvre et se ferme suffit, c'est même plus cohérent avec le style.

---

## ÉTAPE 5 : Le montage dans CapCut

1. **Nouveau projet en 9:16** (1080×1920).
2. **Importe les 25 clips** et place-les dans l'ordre.
3. **Coupe chaque clip** à la durée du script. La plupart des plans de 5 s se coupent à 2 ou 3 s, c'est ce qui donne le rythme.
4. **Voix** : place chaque réplique sur son plan.
5. **Musique** :
   - chiptune rapide à partir du plan 07 ;
   - **coupure totale** au plan 14 ;
   - version épique à partir du plan 19 ;
   - jingle de fin au plan 25.
6. **Effets sonores** : chute, BOUM, SPLATCH, pièces, DOIIING, power-up, prise arrachée. Des banques gratuites comme Pixabay Sounds ou la bibliothèque CapCut suffisent.
7. **Interface** (voir `montage/interface_ui.md`) : ajoute les textes, la barre de vie, les cœurs et les pop-ups « +XP », aux timings du script.
8. **Sous-titres automatiques** : vérifie l'orthographe, police pixel, bien lisibles.
9. **Transitions** : des **coupes sèches** presque partout. Garde un flash blanc pour le plan 01 et un tremblement d'écran pour les impacts.
10. **Vérifie la durée** : entre 60 et 90 s.
11. **Export** en 1080×1920, 30 ou 60 fps, haute qualité.

---

## ÉTAPE 6 : Avant de publier

- [ ] Regarde la vidéo **sur ton téléphone**, en entier, avec puis sans le son.
- [ ] Vérifie la checklist de `montage/checklist.md`.
- [ ] Active le label **« Contenu généré par IA »** sur TikTok.
- [ ] Description courte avec 3 à 5 hashtags (#histoire #pixelart #humour #strasbourg #niveau1).
- [ ] Choisis une **couverture** : la meilleure image du boss ou de Sami qui tombe.

---

## Ordre de travail conseillé (récap)
1. Créer les 4 Elements (une seule fois).
2. Générer le décor « rue » qui manque.
3. Faire les **25 images clés** et les vérifier toutes avant d'animer quoi que ce soit.
4. Tester l'animation sur 2 ou 3 plans difficiles.
5. Animer les 25 plans.
6. Enregistrer les voix.
7. Monter, sonoriser, ajouter l'interface.
8. Vérifier, puis publier.
