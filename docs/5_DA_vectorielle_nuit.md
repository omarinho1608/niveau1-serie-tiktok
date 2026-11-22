# 🌙 Nouvelle DA « vectorielle de nuit » (séries d'angoisse)

⬅️ [Retour à l'accueil](../README.md)

> Remplace le pixel art pour **La Veillée** et **Expéditeur : Toi**.
> Inspirée d'une vidéo de référence (illustration vectorielle plate, très sombre, interface de téléphone, choix interactifs). On reprend **le style** (qui n'appartient à personne) mais **nos propres personnages et créatures**.

---

## 1. Ce qui fait cette DA

| Élément | Description |
|---|---|
| **Dessin** | Illustration **vectorielle 2D plate** : formes simples, aucun contour noir épais, aucune texture, aucun pixel. Personnages très simplifiés (tête ronde, corps en formes géométriques) |
| **Lumière** | Fonds en **dégradés** violet nuit → bleu marine → presque noir, avec un **halo chaud orangé** derrière les personnages ou à l'horizon. Une seule source de lumière |
| **Couleurs** | Fond : `#14121F` → `#2A2340` → halo `#C0603A`. Héros : **une seule couleur vive** pour qu'on le repère toujours. Créatures : **beige pâle / os** `#D9CFBF` |
| **Caméra** | Plans fixes, très centrés, beaucoup d'espace vide. Gros plans sur le **téléphone tenu en main** (la main du héros visible en bas à droite) |
| **Typographie** | Sous-titres en **police condensée très grasse** (type *Bebas Neue* / *Oswald Bold*, libres), blancs, **un mot en rouge** `#E5383B`, 1 à 3 mots à la fois, centrés au milieu de l'écran |
| **Interface (HUD)** | En haut, toujours : petit point rouge + « **NUIT 1 · CHAMBRE** », puis une **horloge géante qui défile à la seconde** (23:52:03 → 23:52:11…) |
| **Téléphone** | Un grand smartphone noir aux bords arrondis, l'écran affiche de vraies interfaces (messages, carte, petites annonces), faites **au montage** |
| **Interactivité** | Écran de **choix** (« TU REGARDES PAR LE JUDAS… OU TU GLISSES LE SWEAT ? ») avec 2 boutons ronds orange / bleu et un **compte à rebours circulaire 3-2-1**, puis **« ◀◀ REMBOBINAGE »** pour montrer l'autre choix |
| **Cartes** | « **RÈGLE N°2** » en blanc sur une étiquette rouge vif, plein écran noir |

---

## 2. Bloc STYLE pour Kling (remplace l'ancien bloc pixel art)

**STYLE :**
```
flat 2D vector illustration, minimalist geometric shapes, simple rounded characters without outlines, no texture, smooth flat color areas, dark night gradient background from deep purple to navy blue to near black, one soft warm orange glow, high contrast, clean modern motion design look, eerie quiet mood, centered composition, vertical 9:16
```

**PROMPT NÉGATIF :**
```
pixel art, pixels, thick black outlines, 3D render, realistic, photorealistic, anime, painterly, sketch, noise, grain, busy background, bright daylight, cheerful colors, gore, blood, text, letters, subtitles, watermark, logo, extra limbs, extra fingers, distorted face, morphing, flickering, low quality
```

---

## 3. Nos personnages dans cette DA (originaux)

> Le héros de la vidéo de référence a une tête noire et un sweat bleu. **Le nôtre est différent** pour ne pas copier.

**Le héros des séries d'angoisse (« toi ») :**
```
a minimalist flat vector character with a perfectly round pale beige head, two small black dot eyes with tiny white highlights, no mouth, round glasses, a bright mustard yellow hoodie with the hood down, dark navy pants, simple rounded white sneakers, no outlines
```
👉 Sa **couleur signature = jaune moutarde** (on le repère en un coup d'œil, et ça rappelle le ciré jaune du narrateur de La Veillée).

**Sa main en vue POV (pour tous les plans téléphone) :**
```
first-person view, a simple flat vector hand in a mustard yellow hoodie sleeve holding a large black smartphone with rounded corners at the bottom right of the frame, the phone screen glowing plain dark grey with no text
```

**Règle pour les créatures :** silhouettes noires très allongées + **un visage pâle couleur os**, simple, avec **un seul détail anormal** (bouche trop large, yeux trop bas, pas de visage du tout…). On ne réutilise **jamais** la créature de la vidéo de référence (le visage ovale fendu aux dents serrées).

---

## 4. Ce qui se fait au montage (pas dans Kling)
- Le **HUD** (point rouge, lieu, horloge qui défile).
- **Toutes les interfaces de téléphone** (bulles de messages, carte avec position, petites annonces) : ce sont des **calques** posés sur l'écran vide du téléphone.
- Les **écrans de choix**, le **compte à rebours** et le **« ◀◀ REMBOBINAGE »**.
- Les **cartes « RÈGLE N° »**.
- Les **sous-titres** (police condensée, mot rouge).

> 💡 Avantage énorme : comme le style est **plat et minimaliste**, une grande partie de la vidéo est du **motion design** (téléphone, textes, choix). Claude Code peut le fabriquer lui-même au montage, et il y a **beaucoup moins de clips à générer dans Kling** (6 à 10 par vidéo au lieu de 15 à 20).

---

## 5. L'animation (référence n°2 : récit historique animé en vectoriel)

> Deuxième référence analysée : une histoire vraie racontée au « tu », en illustration vectorielle plate, avec une **animation très légère mais vivante**. C'est ce niveau d'animation qu'on vise.

### Ce qu'on voit (et qu'on reprend)
| Technique | Ce que ça donne | Comment on le fait |
|---|---|---|
| **Images quasi fixes** | Chaque plan est une illustration ; c'est la voix et le texte qui avancent | Image Kling (pas forcément de vidéo) |
| **Animation « marionnette »** | Les personnages bougent par petits gestes : clignement, tête qui tourne, bras qui porte une cigarette, fumée | Kling Image-to-Video avec un mouvement **minime**, ou découpage perso/fond au montage |
| **Particules d'ambiance** | Poussière qui flotte dans la lumière, fumée, pluie fine, neige | Calque de particules ajouté au montage, en boucle |
| **Lumière vivante** | Ampoule qui pend et grésille, fenêtres d'immeubles qui s'allument, phares qui balaient | Kling (mouvement lent) ou variation de luminosité au montage |
| **Transitions en fondu enchaîné** | Les plans **se fondent** l'un dans l'autre (0,3 à 0,6 s), au lieu de coupes sèches : effet de souvenir, très fluide | Montage |
| **Lent zoom / parallaxe** | La caméra avance doucement ; au premier plan et au fond, les éléments bougent à des vitesses différentes | Montage (zoom) ou Kling (« slow push-in, parallax ») |
| **Titre fort sur la 1re image** | En haut : « HISTOIRE VRAIE · LIEU ANNÉE », puis 1 mot énorme en rouge (« TUE ») et une ligne rouge | Montage |
| **Documents et sources** | Unes de journaux tenues par des mains, encadrés « 25 AOÛT 1973 · … · Source : INA » | Image Kling (journal vierge) + texte au montage |
| **Silhouettes noires** | Les scènes violentes ou anonymes sont montrées en silhouettes plates, jamais en détail | Image Kling |

### Le style des personnages (mise à jour)
Plus « cartoon » que la première référence : **grosse tête ronde, grands yeux ronds avec pupilles**, sourcils épais très expressifs, petit corps simple, aucun contour.

**Bloc STYLE mis à jour (à utiliser à la place du bloc de la section 2) :**
```
flat 2D vector cartoon illustration, minimalist motion design style, characters with big round heads, large round cartoon eyes with black pupils, thick expressive eyebrows, small simple bodies, no outlines, smooth flat colors with soft gradients, warm cinematic lighting (a hanging light bulb, dusk sky, glowing windows), floating dust particles in the light, moody atmosphere, centered composition, vertical 9:16
```

**Héros mis à jour (« toi ») :**
```
a flat vector cartoon young man with a big round head, light brown skin, short black hair, large round cartoon eyes with black pupils, thick eyebrows, small round glasses, a mustard yellow hoodie, dark navy jeans, white sneakers, no outlines
```

### La méthode de production (plus rapide)
1. **Kling, génération d'image uniquement** pour la plupart des plans : fond + personnage, style ci-dessus.
2. **Kling Image-to-Video seulement pour 4 à 6 plans « vivants »**, avec des mouvements **minuscules** : `subtle idle animation, the character blinks and slightly moves his head, smoke rises slowly, dust particles float, almost static camera`.
3. **Claude Code fait le reste au montage** : zoom lent sur chaque image, parallaxe, particules de poussière, scintillement de l'ampoule, fondus enchaînés entre les plans, titres, documents, sources, sous-titres.

> Résultat : beaucoup moins de crédits Kling, un style **cohérent d'un plan à l'autre** (les images fixes ne se déforment pas), et une vidéo qui paraît animée grâce au montage.
