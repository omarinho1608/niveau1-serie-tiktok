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
