# 🎬 Prompt de montage pour Claude Code – La Veillée, épisode 01 « L'Ankou »

⬅️ [Retour à la série](../README.md) · 📝 [Script](script.md) · ▶️ [Prompts Kling](PROMPTS_A_COLLER.md)

## Avant de lancer (5 minutes, sur ton PC Windows)

1. Crée un dossier, par exemple `Documents\Montage_Ankou`.
2. Dedans, crée un sous-dossier **`clips`** et mets-y **une copie** de tes 14 clips Kling, nommés **`D01.mp4` à `D14.mp4`**.
3. *(Optionnel)* Crée un sous-dossier **`sons`** et mets-y des bruitages si tu en as (Pixabay Sounds, gratuit), nommés comme ceci : `vent.mp3`, `grincement.mp3`, `papier.mp3`, `couteau.mp3`, `musique.mp3`. S'il en manque, Claude Code fera sans ou les fabriquera.
4. Ouvre l'application Claude → onglet **Code** → **nouvelle session en Local** → choisis le dossier `Montage_Ankou`.
5. Copie **tout le bloc ci-dessous** (bouton de copie en haut à droite du bloc) et colle-le dans la session.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi mon accord avant d'installer un logiciel.

OBJECTIF
Monter automatiquement une vidéo TikTok verticale (1080x1920, 30 i/s, MP4 H.264 + AAC) de 1 min 50 à 2 min 20, prête à poster : épisode 01 « L'Ankou » de ma série « La Veillée » (légendes du folklore racontées comme un souvenir de famille, ambiance angoissante, pixel art 16-bit nocturne).

RÈGLES DE TRAVAIL
- Travaille UNIQUEMENT dans le dossier où tu es lancé. Ne touche à rien ailleurs.
- Ne modifie jamais les fichiers de clips/ ni de sons/ : travaille sur des copies dans travail/. Mets le résultat final dans sortie/.
- Vérifie toi-même le résultat avant de me dire que c'est fini (voir VÉRIFICATION).
- Ne publie jamais rien.
- Crée un fichier SUIVI.md avec mes règles de montage (celles de ce message, section STYLE). À chaque correction que je te demande, ajoute une règle datée dans SUIVI.md, et relis SUIVI.md avant chaque nouveau montage.

FICHIERS FOURNIS
- clips/D01.mp4 à clips/D14.mp4 : les plans animés (pixel art, 5 ou 10 s chacun, 9:16).
- sons/ (optionnel) : vent.mp3, grincement.mp3, papier.mp3, couteau.mp3, musique.mp3. S'il en manque, fabrique un fond sonore simple avec ffmpeg (vent = bruit brun filtré passe-bas, très bas) et dis-moi lesquels manquent.
Si un clip manque ou a un autre nom, arrête-toi et demande-moi.

OUTILS (Windows, gratuits)
- Python 3, ffmpeg (installation proposée : winget install Gyan.FFmpeg), et le paquet Python edge-tts pour les voix (voix neuronales Microsoft gratuites, il fournit aussi le minutage de chaque mot pour les sous-titres). Pillow pour dessiner les cartes. Police : télécharge « Press Start 2P » (Google Fonts, licence libre) pour les titres et utilise une police grasse lisible (ex. « Montserrat ExtraBold », libre) pour les sous-titres.
- Vérifie ce qui est déjà installé avant de proposer quoi que ce soit.

VOIX (génère-les avec edge-tts, une réplique = un fichier, dans travail/voix/)
- NARRATEUR (« je », jeune adulte, grave, posé, lent) : fr-FR-HenriNeural, rate -8 %, pitch -4Hz.
- YVON (vieux grand-père breton, calme, sec) : fr-FR-RemyMultilingualNeural (ou une autre voix masculine française si indisponible), rate -12 %, pitch -10Hz.
- L'ANKOU (lent, creux, inhumain) : fr-FR-HenriNeural, rate -30 %, puis avec ffmpeg : voix plus grave (asetrate ~0,82 + atempo pour garder la durée), écho (aecho), léger passe-bas.
- LA VOIX DE GRAND-PÈRE REVENU (plan 20) : voix d'Yvon + le même traitement « Ankou » mais plus léger, et plus lointaine (volume plus bas, réverbération).
Laisse 0,4 s de silence entre deux phrases, et 1 s avant chaque révélation (marquées ⏸ ci-dessous).

STYLE (à respecter, référence : chaînes TikTok de folklore narré)
- Rythme : une phrase courte toutes les 2 à 3 s. Le plan dure exactement le temps de sa voix (+ pauses). Si un clip est plus long, coupe-le ; s'il est plus court, ralentis-le légèrement (max 0,8x) puis fige la dernière image.
- Mouvement : ajoute un zoom avant très lent (Ken Burns, ~3 % sur la durée du plan) sur chaque plan et chaque carte. Coupes sèches entre les plans. Un fondu au noir de 0,5 s uniquement avant le plan 18 (retour au présent) et à la toute fin.
- SOUS-TITRES incrustés, mot à mot (groupes de 1 à 3 mots, synchronisés sur le minutage edge-tts), centrés horizontalement, à 62 % de la hauteur de l'image. Police grasse, blanche, contour noir épais, légère ombre. UN mot-clé par phrase en orange-rouge (#FF5A36) : le mot le plus fort (ex. « règle », « charrette », « Mort », « aide-moi », « couteau », « 31 décembre »). Petite animation d'apparition (pop 90 % → 100 % en 0,1 s) si c'est simple à faire en ASS. Pas de sous-titres sur les cartes (le texte de la carte suffit), sauf la voix off.
- Couleurs : ne change pas les couleurs des clips (déjà sombres). Ajoute un léger vignettage.
- SON : fond de vent continu très bas (-30 dB). Musique sombre (drone) si fournie, à -28 dB, qui s'arrête net au plan 20. Les voix toujours bien au-dessus (baisse automatique du fond quand on parle). Volume final normalisé à -14 LUFS.

CARTES À DESSINER (Pillow, 1080x1920, PNG dans travail/cartes/)
- FICHE (plan 2, en superposition sur le clip D02, fond légèrement assombri) : en haut, « L'ANKOU » en très grand (police pixel, blanc cassé) ; dessous en rouge « [ FINISTÈRE · BRETAGNE ] » ; une jauge « NIVEAU DE DANGER » de 12 cases pixel allant du vert au rouge, toutes allumées, avec le mot « MORTEL » ; en bas, en petit rouge : « LE SERVITEUR DE LA MORT. IL VIENT CHERCHER LES ÂMES AVEC SA CHARRETTE. »
- 3 CARTES RÈGLES (plans 5, 6, 7) : grande feuille de parchemin beige pixel au centre sur fond noir, petit tampon « RÈGLE 1 » (2, 3) en haut à gauche, texte noir centré :
  RÈGLE 1 : « Ne siffle jamais la nuit. Ça l'appelle. »
  RÈGLE 2 : « Si tu entends grincer une charrette, ne la regarde pas. »
  RÈGLE 3 : « S'il te demande de l'aide, aide-le. Mais ne prends jamais rien de sa main. »
- CARTE FINALE (plan 22) : fond noir, titre « 📜 D'OÙ VIENT LA LÉGENDE » (sans emoji si la police ne le gère pas), texte blanc : « L'Ankou est une figure du folklore breton. L'écrivain Anatole Le Braz a recueilli des dizaines de récits à son sujet dans "La Légende de la mort" (1893). On y raconte qu'il conduit une charrette qui grince, et que le dernier mort de l'année dans une paroisse devient l'Ankou de l'année suivante. » Puis, en orange-rouge : « Dans ta famille, quelle règle on te répétait ? 👇 » (flèche dessinée si pas d'emoji).

SCRIPT (plan · clip · voix · sons)
1 · D01 · NARRATEUR : « En Bretagne, les anciens ont une règle. » / « La nuit, si tu entends grincer une charrette… ne te retourne pas. » · vent, grincement très lointain
2 · D02 + FICHE · NARRATEUR : « On l'appelle l'Ankou. » / « Le serviteur de la Mort. »
3 · D03 · NARRATEUR : « Mon grand-père, Yvon, vivait seul près de Plouguerneau. » / « J'y passais tous mes étés. » · feu de cheminée
4 · D03 (suite) · NARRATEUR : « Il me répétait trois règles. »
5 · CARTE RÈGLE 1 · (pas de voix, 3 s) · papier
6 · CARTE RÈGLE 2 · (pas de voix, 3 s) · papier
7 · CARTE RÈGLE 3 · (3 s) puis NARRATEUR : « Je trouvais ça idiot. J'avais douze ans. » · papier
8 · D04 · NARRATEUR : « Un soir d'août, on rentrait à pied de la fête du village. » / « Et moi, je sifflais. » · un petit sifflement (fabrique-le avec un son sinusoïdal court si besoin)
9 · D04 (suite) · NARRATEUR : « Grand-père s'est arrêté net. » ⏸ YVON : « Tais-toi. »
10 · D05 · NARRATEUR : « Derrière nous, une charrette. » / « Elle grinçait. » · grincement qui se rapproche
11 · D06 · NARRATEUR : « Entre les doigts de grand-père, j'ai regardé. » ⏸ « Je n'aurais pas dû. »
12 · D07 · NARRATEUR : « Elle s'est arrêtée à notre hauteur. » · grincement qui s'arrête
13 · D08 (1re moitié) · L'ANKOU : « La cheville de l'essieu… s'est brisée. » ⏸ « Aide-moi. »
14 · D09 · NARRATEUR : « Grand-père n'a pas discuté. » / « Il a coupé une branche dans la haie. Il l'a taillée avec son propre couteau. » · couteau sur bois
15 · D08 (2e moitié) · L'ANKOU : « Prends le mien. Il coupe mieux. » / NARRATEUR : « Grand-père n'a même pas regardé le couteau. » / YVON : « Le mien suffira. »
16 · D10 · L'ANKOU : « Tu connais les règles, Yvon. » ⏸ « On se reverra. Une seule fois. » · grincement qui s'éloigne
17 · D11 · NARRATEUR : « Il n'en a plus jamais parlé. » / « Mais il ne m'a plus jamais laissé siffler. » · silence presque total
— fondu au noir 0,5 s —
18 · D12 · NARRATEUR : « Grand-père est mort le 31 décembre. Le dernier jour de l'année. » / « Ici, on dit que le dernier mort de l'année devient l'Ankou… pour toute l'année suivante. »
19 · D12 (suite) · NARRATEUR : « Ce soir, je dors seul dans sa ferme. » · un grincement, au loin
20 · D13 · SILENCE TOTAL (musique coupée, vent coupé) 1 s, puis VOIX DE GRAND-PÈRE REVENU : « Petit… la cheville s'est brisée. » ⏸ « Aide-moi. »
21 · D14 · NARRATEUR : « J'ai son couteau. » / « Mais je ne sais plus… si la règle compte encore, quand c'est lui qui demande. » · respiration
22 · CARTE FINALE · (5 s, pas de voix) · le vent revient très doucement

VÉRIFICATION (obligatoire avant de me dire que c'est fini)
1. Durée totale entre 1 min 50 et 2 min 20 (jamais sous 1 min). Résolution 1080x1920.
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
