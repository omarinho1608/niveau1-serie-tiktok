# 🎬 Prompt de montage pour Claude Code – La Veillée, épisode 01 « L'Ankou »

⬅️ [Retour à la série](../README.md) · 📝 [Script](script.md) · ▶️ [Prompts Kling](PROMPTS_A_COLLER.md)

## Avant de lancer (5 minutes, sur ton PC Windows)

1. Crée un dossier, par exemple `Documents\Montage_Ankou`.
2. Dedans, crée un sous-dossier **`clips`** et mets-y **une copie** de tes 17 clips Kling, nommés **`D01.mp4` à `D17.mp4`**.
3. *(Optionnel)* Crée un sous-dossier **`sons`** et mets-y des bruitages si tu en as (Pixabay Sounds, gratuit), nommés comme ceci : `vent.mp3`, `grincement.mp3`, `papier.mp3`, `couteau.mp3`, `grillons.mp3`, `coups_porte.mp3`, `claque.mp3`, `musique.mp3`. S'il en manque, Claude Code fera sans ou les fabriquera.
4. Ouvre l'application Claude → onglet **Code** → **nouvelle session en Local** → choisis le dossier `Montage_Ankou`.
5. Copie **tout le bloc ci-dessous** (bouton de copie en haut à droite du bloc) et colle-le dans la session.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi mon accord avant d'installer un logiciel.

OBJECTIF
Monter automatiquement une vidéo TikTok verticale (1080x1920, 30 i/s, MP4 H.264 + AAC) d'environ 1 min 55 (entre 1 min 45 et 2 min 10), prête à poster : épisode 01 « L'Ankou » de ma série « La Veillée » (légendes du folklore racontées comme un souvenir de famille, ambiance angoissante, pixel art 16-bit nocturne).

RÈGLES DE TRAVAIL
- Travaille UNIQUEMENT dans le dossier où tu es lancé. Ne touche à rien ailleurs.
- Ne modifie jamais les fichiers de clips/ ni de sons/ : travaille sur des copies dans travail/. Mets le résultat final dans sortie/.
- Vérifie toi-même le résultat avant de me dire que c'est fini (voir VÉRIFICATION).
- Ne publie jamais rien.
- Crée un fichier SUIVI.md avec mes règles de montage (celles de ce message, section STYLE). À chaque correction que je te demande, ajoute une règle datée dans SUIVI.md, et relis SUIVI.md avant chaque nouveau montage.

FICHIERS FOURNIS
- clips/D01.mp4 à clips/D17.mp4 : les plans animés (pixel art, 5 ou 10 s chacun, 9:16). Certains clips servent deux fois (voir SCRIPT).
- sons/ (optionnel) : vent.mp3, grincement.mp3, papier.mp3, couteau.mp3, grillons.mp3, coups_porte.mp3, claque.mp3, musique.mp3. S'il en manque, fabrique un fond sonore simple avec ffmpeg (vent = bruit brun filtré passe-bas, très bas) et dis-moi lesquels manquent.
Si un clip manque ou a un autre nom, arrête-toi et demande-moi.

OUTILS (Windows, gratuits)
- Python 3, ffmpeg (installation proposée : winget install Gyan.FFmpeg), et le paquet Python edge-tts pour les voix (voix neuronales Microsoft gratuites, il fournit aussi le minutage de chaque mot pour les sous-titres). Pillow pour dessiner les cartes. Police : télécharge « Press Start 2P » (Google Fonts, licence libre) pour les titres et utilise une police grasse lisible (ex. « Montserrat ExtraBold », libre) pour les sous-titres.
- Vérifie ce qui est déjà installé avant de proposer quoi que ce soit.

VOIX (génère-les avec edge-tts, une réplique = un fichier, dans travail/voix/)
- NARRATEUR (« je », jeune adulte, grave, tendu, parle AU PRÉSENT, phrases courtes, débit un peu rapide pour garder la tension) : fr-FR-HenriNeural, rate -8 %, pitch -4Hz.
- YVON (vieux grand-père breton, calme, sec) : fr-FR-RemyMultilingualNeural (ou une autre voix masculine française si indisponible), rate -12 %, pitch -10Hz.
- L'ANKOU (lent, creux, inhumain) : fr-FR-HenriNeural, rate -30 %, puis avec ffmpeg : voix plus grave (asetrate ~0,82 + atempo pour garder la durée), écho (aecho), léger passe-bas.
- LA VOIX DE GRAND-PÈRE REVENU (plan 20) : voix d'Yvon + le même traitement « Ankou » mais plus léger, et plus lointaine (volume plus bas, réverbération).
Laisse 0,4 s de silence entre deux phrases, et 1 s avant chaque révélation (marquées ⏸ ci-dessous).

STYLE (à respecter, référence : chaînes TikTok de folklore narré)
- Rythme : NERVEUX. Une phrase courte toutes les 1,5 à 2,5 s, jamais de temps mort sauf les silences ⏸ voulus. Le plan dure exactement le temps de sa voix (+ pauses). Si un clip est plus long, coupe-le ; s'il est plus court, ralentis-le légèrement (max 0,8x) puis fige la dernière image.
- Mouvement : ajoute un zoom avant très lent (Ken Burns, ~3 % sur la durée du plan) sur chaque plan et chaque carte. Coupes sèches entre les plans. Un fondu au noir de 0,5 s uniquement avant le plan 19 et à la toute fin. Petit tremblement d'image (shake 0,3 s) sur les chocs : coups à la porte (plans 1 et 21), la claque (plan 16).
- SOUS-TITRES incrustés, mot à mot (groupes de 1 à 3 mots, synchronisés sur le minutage edge-tts), centrés horizontalement, à 62 % de la hauteur de l'image. Police grasse, blanche, contour noir épais, légère ombre. UN mot-clé par phrase en orange-rouge (#FF5A36) : le mot le plus fort (ex. « règle », « charrette », « Mort », « aide-moi », « couteau », « 31 décembre »). Petite animation d'apparition (pop 90 % → 100 % en 0,1 s) si c'est simple à faire en ASS. Pas de sous-titres sur les cartes (le texte de la carte suffit), sauf la voix off.
- Couleurs : ne change pas les couleurs des clips (déjà sombres). Ajoute un léger vignettage.
- SON : fond de vent continu très bas (-30 dB). Musique sombre (drone) si fournie, à -28 dB, qui s'arrête net au plan 20. Les voix toujours bien au-dessus (baisse automatique du fond quand on parle). Volume final normalisé à -14 LUFS.

CARTES À DESSINER (Pillow, 1080x1920, PNG dans travail/cartes/)
- FICHE (plan 3, en superposition sur le clip D02, fond légèrement assombri) : en haut, « L'ANKOU » en très grand (police pixel, blanc cassé) ; dessous en rouge « [ FINISTÈRE · BRETAGNE ] » ; une jauge « NIVEAU DE DANGER » de 12 cases pixel allant du vert au rouge, toutes allumées, avec le mot « MORTEL » ; en bas, en petit rouge : « LE SERVITEUR DE LA MORT. IL VIENT CHERCHER LES ÂMES AVEC SA CHARRETTE. »
- TAMPONS « RÈGLE 1 ✗ » (plan 8) et « RÈGLE 2 ✗ » (plan 11) : petit tampon rouge incliné qui s'écrase en haut à droite pendant 1,5 s, avec un bruit sourd.
- 3 CARTES RÈGLES (plans 5, 6, 7) : grande feuille de parchemin beige pixel au centre sur fond noir, petit tampon « RÈGLE 1 » (2, 3) en haut à gauche, texte noir centré :
  RÈGLE 1 : « Ne siffle jamais la nuit. »
  RÈGLE 2 : « Ne regarde jamais la charrette. »
  RÈGLE 3 : « Ne prends jamais rien de sa main. »
- CARTE FINALE (plan 24) : fond noir, titre « 📜 D'OÙ VIENT LA LÉGENDE » (sans emoji si la police ne le gère pas), texte blanc : « L'Ankou est une figure du folklore breton. L'écrivain Anatole Le Braz a recueilli des dizaines de récits à son sujet dans "La Légende de la mort" (1893). On y raconte qu'il conduit une charrette qui grince, et que le dernier mort de l'année dans une paroisse devient l'Ankou de l'année suivante. » Puis, en orange-rouge : « Tu prends ce qu'il te tend ? 👇 » (flèche dessinée si pas d'emoji).

SCRIPT V2 (plan · clip · voix · sons) — ⏸ = 1 s de silence
1 · D13 · 3 coups à la porte (+ shake) · NARRATEUR : « Mon grand-père est mort il y a trois jours. » / « Ce soir… il frappe à ma porte. »
2 · D01 · vent, grincement lointain · NARRATEUR : « En Bretagne, on a une règle. » / « Si une charrette grince derrière toi, la nuit… ne te retourne pas. »
3 · D02 + FICHE · NARRATEUR : « L'Ankou. » / « Le serviteur de la Mort. »
4 · D03 · feu de cheminée · NARRATEUR : « Grand-père m'avait donné trois règles. » ⏸ « Je les ai toutes brisées. »
5 · CARTE RÈGLE 1 · papier · YVON lit : « Ne siffle jamais la nuit. »
6 · CARTE RÈGLE 2 · papier · YVON : « Ne regarde jamais la charrette. »
7 · CARTE RÈGLE 3 · papier · YVON : « Et ne prends jamais rien… de sa main. »
8 · D04 · NARRATEUR : « J'ai douze ans. On rentre de la fête, à pied. » · l'enfant siffle (son sinusoïdal court si besoin) · TAMPON « RÈGLE 1 ✗ »
9 · D04 (fin) · grillons qui s'arrêtent net · NARRATEUR : « D'un coup… les grillons se taisent. » ⏸ YVON (chuchoté) : « Tais-toi. »
10 · D05 · grincement qui se rapproche · NARRATEUR : « Derrière nous, ça grince. » / « Et pour la première fois… la main de grand-père tremble. »
11 · D06 · NARRATEUR : « Je regarde entre ses doigts. » · TAMPON « RÈGLE 2 ✗ » · « Un cheval qui n'a plus que les os. » / « Et sur le banc… quelque chose de trop grand pour être un homme. »
12 · D07 · la charrette s'arrête net · NARRATEUR : « Elle s'arrête. Juste à côté de nous. »
13 · D08 (1re moitié) · L'ANKOU : « Yvon. » ⏸ NARRATEUR : « Il connaît son prénom. » / L'ANKOU : « La cheville s'est brisée. Aide-moi. »
14 · D09 · couteau sur bois · NARRATEUR : « Grand-père taille une branche. Vite. » / « Avec son propre couteau. »
15 · D08 (2e moitié) · L'ANKOU : « Toi, petit… prends le mien. »
16 · D15 · NARRATEUR : « Ma main se tend toute seule. » · claque (+ shake) · YVON (crie) : « Ne touche pas ! »
17 · D16 · L'ANKOU : « L'enfant m'a appelé. » / « Quelqu'un doit monter. » ⏸ YVON : « Alors ce sera moi. » / « Pas lui. »
18 · D10 · L'ANKOU : « Un 31 décembre, Yvon. » / « Je reviendrai. » · grincement qui s'éloigne, puis les grillons reprennent doucement
— fondu au noir 0,5 s —
19 · D11 · NARRATEUR : « Il n'en a jamais reparlé. » / « Mais chaque 31 décembre, il veillait toute la nuit. Devant la porte. »
20 · D12 · NARRATEUR : « Cette année, il s'est endormi. » / « Ici, on dit que le dernier mort de l'année devient l'Ankou. »
21 · D13 · SILENCE TOTAL (musique et vent coupés) 1 s, puis 3 coups à la porte (+ shake) · VOIX DE GRAND-PÈRE REVENU : « Petit… » ⏸ « La cheville s'est brisée. » / « Aide-moi. »
22 · D14 · respiration · NARRATEUR : « J'ai son couteau. » / « Je n'ouvre pas. »
23 · D17 · NARRATEUR : « Alors il glisse sa main sous la porte. » / « Il me tend quelque chose. » ⏸ « Règle numéro trois. » / « Mais c'est la main de mon grand-père. »
24 · CARTE FINALE · (6 s, pas de voix) · le vent revient très doucement

VÉRIFICATION (obligatoire avant de me dire que c'est fini)
1. Durée totale entre 1 min 45 et 2 min 10 (jamais sous 1 min). Résolution 1080x1920.
2. Extrais une image toutes les 10 s dans travail/controle/ et REGARDE-les : sous-titres lisibles, dans le cadre, mot-clé en couleur, cartes bien affichées, pas d'image noire imprévue.
3. Vérifie le son : aucune voix coupée, pas de saturation, volume final ~ -14 LUFS (mesure-le avec ffmpeg loudnorm/ebur128).
4. Vérifie que chaque plan est dans le bon ordre (compare avec le SCRIPT).
5. Donne-moi un petit rapport : durée, ce qui a marché, ce que tu n'as pas pu faire (ex. un son manquant), et le chemin de la vidéo finale (sortie/ankou_ep01_v1.mp4).

ENSUITE
Je regarde la vidéo et je te dis ce qui ne va pas. Tu notes chaque correction comme règle datée dans SUIVI.md, tu corriges, et tu exportes une nouvelle version (v2, v3…) sans écraser les anciennes.
```

---

## Après le montage
- Regarde la vidéo **sur ton téléphone**, avec et sans le son.
- Dis à Claude Code ce qui ne va pas, en langage simple (« les sous-titres sont trop petits », « la voix de l'Ankou fait robot »…). Il corrige et note la règle pour les prochains épisodes.
- Pour les prochains épisodes de La Veillée, garde le même dossier : `SUIVI.md` contiendra déjà toutes tes préférences.
