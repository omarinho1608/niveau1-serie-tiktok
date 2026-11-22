# 🎬 PROMPT DE MONTAGE COMPLET – La Veillée, épisode 02 « Aïcha Kandicha »

⬅️ [Retour à l'épisode](script.md) · 🖼️ [Images et clips générés](rendus/)

> **Tout est dedans** : les fichiers à utiliser, le script mot pour mot, les voix, le HUD, les cartes, les effets, les sons, l'export et la vérification.
> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code** (sur ton ordinateur ou dans le cloud). Il récupère lui-même les images et les clips sur GitHub.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel. Ne publie jamais rien. Vérifie toi-même le résultat avant de me dire que c'est fini.

=====================================================================
0. RÉCUPÉRER LES FICHIERS
=====================================================================
Clone le dépôt GitHub omarinho1608/niveau1-serie-tiktok, branche claude/pensive-ramanujan-14exqk (git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok).
Crée un dossier de travail montage_ep02/ (en dehors du dépôt) avec : sources/ (copie), travail/, sortie/.
Copie dans montage_ep02/sources/ :
- la_veillee/ep02_aicha_kandicha/rendus/images/I01.png … I20.png  (768x1360 environ, 9:16, illustrations vectorielles plates)
- la_veillee/ep02_aicha_kandicha/rendus/clips/V01.mp4, V04.mp4, V08.mp4, V09.mp4, V12.mp4, V17.mp4  (720p, 9:16, SANS son ; V01 = 5 s, les autres = 4 s)
Ne modifie jamais les originaux. Si un fichier manque, arrête-toi et dis-le-moi.
S'il existe un fichier SUIVI.md (mes règles de montage), relis-le et applique-le. Sinon crée-le avec la section STYLE ci-dessous. À chaque correction que je te donne, ajoute une règle datée dans SUIVI.md.

=====================================================================
1. OUTILS (gratuits)
=====================================================================
- ffmpeg (Windows : winget install Gyan.FFmpeg ; Mac : brew install ffmpeg ; Linux : apt install ffmpeg)
- Python 3 + paquets : edge-tts (voix), Pillow (cartes et HUD), numpy. Optionnel : rembg (détourage pour la parallaxe).
- Polices libres (Google Fonts) : « Bebas Neue » (sous-titres, HUD, titres) et « Inter » ou « Montserrat » (petits textes).
- Si edge-tts n'arrive pas à se connecter et qu'il y a un proxy HTTPS dans l'environnement, lance-le avec --proxy "$HTTPS_PROXY".

=====================================================================
2. LA VIDÉO À OBTENIR
=====================================================================
TikTok vertical 1080x1920, 30 i/s, H.264 (CRF 18, preset slow, yuv420p) + AAC 192 kb/s, durée 2 min 10 à 2 min 40.
Fichier final : sortie/aicha_ep02_v1.mp4 (les versions suivantes : v2, v3… sans jamais écraser).
Histoire : légende marocaine racontée au « tu », angoissante, avec un compte à rebours jusqu'au lever du soleil. Elle finit sur un choix A/B (partie 1).

=====================================================================
3. STYLE D'ANIMATION (le plus important)
=====================================================================
La plupart des plans sont des IMAGES FIXES : tu les fais vivre, comme les récits animés vectoriels sur TikTok.
- Mise à l'échelle : chaque image/clip est agrandi pour REMPLIR 1080x1920 (scale puis crop au centre, jamais de bandes noires).
- Zoom avant lent sur chaque image fixe : 100 % → 106 % sur la durée du plan (zoompan ou scale animé, fluide, sans saccade). Varie le point de zoom selon le plan (visage, mains, sabots, objet important).
- Respiration : sur les gros plans de visage (I02, I13), légère oscillation d'échelle ±0,6 % toutes les 3 s.
- Parallaxe (si rembg fonctionne) : sur I02, I05, I06, I10, I13, I14, sépare le personnage du fond et fais bouger le fond un peu moins vite. Sinon, zoom simple.
- Particules : calque de petites particules claires (poussière/brume) qui montent lentement, sur TOUTE la vidéo, opacité 25 à 35 %. Génère-le toi-même (Python ou ffmpeg).
- Brume : calque de brume douce qui glisse lentement de gauche à droite sur tous les plans de l'oued (I01, I07 à I20).
- Lumière vivante : léger scintillement irrégulier (±4 % de luminosité) sur les plans avec une lampe à huile (I04/V04, I05, I15, I16).
- Clips animés : V01, V04, V08, V09, V12, V17 remplacent l'image du même numéro. Coupe-les ou ralentis-les (max 0,8x, avec interpolation douce) pour coller à la voix. Si un plan est plus long que le clip, fige la dernière image et continue le zoom lent.
- Transitions : FONDU ENCHAÎNÉ 0,4 s entre les plans calmes. COUPE SÈCHE + tremblement d'image 0,3 s sur les chocs (plans 16, 17, 22). Fondu au noir 0,6 s à la toute fin.
- Vignettage léger sur toute la vidéo. Ne change pas les couleurs des images.
- Règle d'or : jamais plus de 2,5 s sans changement visible (nouvelle image, nouveau point de zoom, texte qui apparaît, HUD qui saute).

=====================================================================
4. LE HUD (en haut de l'écran, pendant toute la vidéo SAUF sur les cartes plein écran)
=====================================================================
- En haut à gauche (marge 60 px) : un petit drapeau du Maroc dessiné simplement (rectangle rouge + étoile verte) + l'heure réelle en blanc, police Bebas Neue 64 px (ex. « 05:21 »).
- En haut à droite : un encadré noir semi-transparent à bord rouge (#E5383B), avec en petit « ☀ SOLEIL » et en dessous un compte à rebours en gros chiffres blancs (Bebas Neue 84 px) au format MM:SS (ex. « 42:00 »).
- Le compte à rebours DÉFILE À LA SECONDE pendant la vidéo (1 seconde de vidéo = 1 seconde en moins). Il SAUTE aux valeurs indiquées dans le script : au moment du saut, glitch de 0,2 s (décalage RVB + scintillement) + petit bruit « tic ».
- Il ne remonte jamais. Plan 19 : il défile en accéléré de 29:40 à 11:58 en 2 s, pendant que l'heure passe de 05:33 à 05:51.
- Plans 23 à 25 : le compte à rebours passe en ROUGE et pulse légèrement (échelle 100 → 104 % chaque seconde). Plan 26 : il se FIGE à 02:41.
- Garde la zone du HUD lisible : léger dégradé sombre en haut de l'écran (noir 40 % → transparent sur 260 px).

=====================================================================
5. SOUS-TITRES
=====================================================================
- Mot à mot, groupes de 1 à 3 mots, synchronisés sur le minutage des mots fourni par edge-tts (WordBoundary). Jamais en retard sur la voix.
- Centrés horizontalement, à 62 % de la hauteur. Bebas Neue 96 px, blanc, ombre douce noire (pas de gros contour).
- UN mot-clé par phrase en JAUNE MOUTARDE #F2B33D (le mot le plus fort : prénom, « sabots », « fer », « soleil », « règle », chiffres…).
- Petite animation d'apparition : échelle 90 % → 100 % en 0,08 s.
- Pas de sous-titres sur les cartes de règles (le texte de la carte suffit), mais OUI pour la voix off des autres plans.
- Les chuchotements d'Aïcha : sous-titres en italique, plus petits (72 px), couleur vert pâle #9FE0C0.

=====================================================================
6. VOIX (edge-tts, une réplique = un fichier dans travail/voix/)
=====================================================================
- NARRATEUR (au « tu », présent, tendu ; plus rapide dans l'action, plus lent dans les silences) : fr-FR-HenriNeural, rate -5 %, pitch -4Hz. Plans d'action (11, 15, 20, 23) : rate +5 %.
- MIMA (vieille grand-mère marocaine, douce et terrifiée) : fr-FR-VivienneMultilingualNeural (sinon fr-FR-DeniseNeural), rate -15 %, pitch -6Hz.
- KARIM (ado de 17 ans en transe, voix vide et monotone) : fr-FR-RemyMultilingualNeural (sinon une autre voix masculine différente du narrateur), rate -20 %, pitch +2Hz.
- AÏCHA (douce, envoûtante, inquiétante) : fr-FR-DeniseNeural, rate -25 %, puis ffmpeg : réverbération (aecho=0.8:0.85:60|120:0.35|0.25) + léger chorus. Chuchotements « à l'oreille » (plans 18 et 21 de la fausse Mima) : volume plus bas, filtre passe-haut léger, placés à 85 % d'un seul côté en stéréo.
- FAUSSE MIMA (plan 21) : voix de Mima + le même traitement qu'Aïcha, pitch encore -2Hz.
- Le prénom du héros chuchoté : « Ilyas ».
- Silences : 0,35 s entre deux phrases ; ⏸ = 1 s de silence avant une révélation.
- Les voix sont toujours bien au-dessus du fond sonore (ducking du fond de -8 dB pendant que quelqu'un parle).

=====================================================================
7. SONS ET MUSIQUE
=====================================================================
Si le dossier sources/sons/ contient des fichiers (eau.mp3, grenouilles.mp3, chiens.mp3, vent.mp3, pas.mp3, coeur.mp3, choc.mp3, cri.mp3, tic.mp3, papier.mp3, musique.mp3), utilise-les. Sinon FABRIQUE-LES avec ffmpeg/Python et dis-moi lesquels sont fabriqués :
- Ambiance eau/vent : bruit brun filtré passe-bas (~400 Hz) + modulation lente, très bas (-30 dB), en continu.
- Grenouilles/insectes de nuit : petits clics et coassements synthétiques irréguliers, (-28 dB), du début jusqu'au plan 12 où ils S'ARRÊTENT NET.
- Pas rapides (plan 11) : impulsions sourdes rythmées.
- Battement de cœur : double impulsion grave (« boum-boum »), discret à partir du plan 20, qui accélère jusqu'au plan 25.
- Choc sourd (révélations des sabots, plans 16 et 22, tampons) : impulsion grave 50 Hz + bruit court.
- Tic du compte à rebours (quand le HUD saute, et chaque seconde sur l'écran de choix) : clic aigu court.
- Papier (cartes de règles) : bruit blanc filtré très court.
- Musique : drone sombre (2 ou 3 sinusoïdes graves désaccordées + bruit filtré) qui monte doucement du plan 13 au plan 25 (-26 dB → -16 dB), puis COUPURE NETTE au plan 26.
- Plan 17 : SILENCE TOTAL (seulement la voix).
- Mixage final normalisé à -14 LUFS intégrés, crête max -1 dBTP.

=====================================================================
8. CARTES PLEIN ÉCRAN (dessinées avec Pillow, 1080x1920, style plat vectoriel)
=====================================================================
- FICHE (plan 5) sur I01 flouté (gaussien 18 px) et assombri 50 % : en haut « AÏCHA KANDICHA » (Bebas Neue 150 px, blanc cassé #F2EDE4) ; dessous en rouge #E5383B « [ RÉGION DE MEKNÈS · MAROC ] » (48 px) ; une jauge « NIVEAU DE DANGER » de 12 cases arrondies du vert au rouge, toutes allumées, avec le mot « MORTEL » à droite ; en bas, en petit rouge (40 px, centré) : « ELLE APPELLE LES HOMMES PAR LEUR PRÉNOM. ELLE REPART AU LEVER DU SOLEIL. » Animation : la fiche glisse depuis le bas en 0,3 s, la jauge se remplit case par case.
- RÈGLES (plans 7 à 10) : fond noir #0E0E12, une étiquette rouge vif arrondie « RÈGLE N°1 » (2, 3, 4) en Bebas Neue 110 px blanc, et dessous le texte de la règle en blanc (Bebas Neue 80 px, centré, 3 lignes max) :
  N°1 « NE RÉPONDS JAMAIS À TON PRÉNOM. »
  N°2 « SI TU DOUTES… REGARDE SES PIEDS. »
  N°3 « LE FER LA FAIT FUIR. MAIS CELUI QUI LA CHASSE, ELLE NE L'OUBLIE JAMAIS. »
  N°4 « AU LEVER DU SOLEIL, ELLE DOIT RENTRER DANS L'EAU. TIENS JUSQUE-LÀ. »
  Animation : l'étiquette tombe et rebondit légèrement (0,25 s), bruit de papier.
- TAMPONS : « RÈGLE N°1 ✗ » (rouge) au plan 14 et « RÈGLE N°2 ✓ » (vert #3BB273) au plan 22 : tampon incliné de -8°, en haut à droite sous le HUD, qui s'écrase (échelle 130 → 100 % en 0,12 s) avec un choc sourd, visible 1,5 s.
- « 18 MINUTES PLUS TARD » (plan 19) : texte blanc Bebas Neue 120 px sur fond noir, pendant que le HUD défile en accéléré.
- ÉCRAN DE CHOIX (plan 26) sur I20 flouté et assombri : « TU FAIS QUOI ? » (Bebas Neue 140 px, blanc) ; deux gros boutons arrondis : orange #F28C28 « [A] JE PLANTE LE FER » et bleu #2F6BFF « [B] JE TIENS JUSQU'AU SOLEIL » ; en dessous, un compte à rebours circulaire rouge 3 → 2 → 1 (anneau qui se vide, tic à chaque seconde) ; en bas « VOTE EN COMMENTAIRE · PARTIE 2 BIENTÔT » (52 px). Durée 7 à 8 s.
- CARTE FINALE (plan 27) : fond noir, titre « D'OÙ VIENT LA LÉGENDE » (Bebas Neue 90 px, jaune moutarde), texte blanc (Inter 44 px, centré, interligne 1,35) : « Aïcha Kandicha est une figure du folklore marocain. On la décrit comme une femme d'une grande beauté, aux pieds de chèvre ou de chameau, qui hante les points d'eau et appelle les hommes par leur prénom. Selon la tradition, elle craint le fer. » Puis, en bas en orange-rouge : « Et toi, tu fais quoi : A ou B ? 👇 » (dessine la flèche si l'emoji ne s'affiche pas). Durée 6 s.

=====================================================================
9. SCRIPT COMPLET (plan · visuel · HUD heure / compte à rebours · voix et sons)  —  ⏸ = 1 s de silence
=====================================================================
1 · V01 · 05:21 / 42:00 · eau, grenouilles · NARRATEUR : « Il est 5 h 21. » / « Quelqu'un appelle ton cousin par son prénom. » / « Depuis l'oued. »
2 · I02 · 05:21 · AÏCHA (douce, lointaine) : « Kariiim… »
3 · I03 · 05:22 / saute à 41:02 · NARRATEUR : « Tu es en vacances chez ta grand-mère, près de Meknès. » / « Le lit de Karim est vide. La fenêtre est ouverte. »
4 · V04 · 05:22 · NARRATEUR : « Mima est déjà réveillée. » / « Ses mains tremblent. » / MIMA : « Elle est revenue. »
5 · FICHE (sur I01 flouté) · NARRATEUR : « Aïcha Kandicha. »
6 · I05 · 05:23 / saute à 40:15 · MIMA : « Mes jambes ne me portent plus. C'est toi qui vas y aller. » / « Écoute-moi bien. »
7 · RÈGLE N°1 · MIMA : « Ne réponds jamais à ton prénom. »
8 · RÈGLE N°2 · MIMA : « Si tu doutes… regarde ses pieds. »
9 · RÈGLE N°3 · MIMA : « Le fer la fait fuir. Mais celui qui la chasse… elle ne l'oublie jamais. »
10 · RÈGLE N°4 · MIMA : « Au lever du soleil, elle doit rentrer dans l'eau. Tiens jusque-là. »
11 · I06 · 05:25 / saute à 37:48 · pas rapides, souffle · NARRATEUR : « Tu cours. » / « Le chemin vers l'oued fait huit cents mètres. » / « Tu ne l'as jamais trouvé aussi long. »
12 · I07 · 05:29 / saute à 33:30 · grenouilles et chiens S'ARRÊTENT NET · NARRATEUR : « D'un coup, les grenouilles se taisent. » / « Même les chiens du village. » ⏸ « Plus rien ne bouge. »
13 · V08 · 05:30 · la musique drone commence · NARRATEUR : « Karim est dans l'eau. Jusqu'aux genoux. » / « Il avance. » / « Il ne cligne pas des yeux. »
14 · V09 · 05:30 / saute à 32:05 · AÏCHA : « Kariiim… viens. » / KARIM (absent, monotone) : « …J'arrive. » · TAMPON « RÈGLE N°1 ✗ »
15 · I10 · 05:31 · éclaboussures · NARRATEUR : « Tu l'attrapes par le bras. » / « Il te repousse. » / « Il est deux fois plus fort que d'habitude. »
16 · I11 · 05:32 / saute à 30:11 · NARRATEUR : « Tu fais ce que Mima a dit. » / « Tu regardes ses pieds. » ⏸ CHOC + zoom coup de poing (105 → 115 % en 0,15 s) + tremblement · « Des sabots. »
17 · V12 · 05:32 · SILENCE TOTAL · NARRATEUR (bas) : « Elle a vu que tu avais vu. »
18 · I13 · 05:33 / saute à 29:40 · AÏCHA (chuchoté à l'oreille) : « Ilyas… » / NARRATEUR : « Maintenant, c'est ton prénom qu'elle chuchote. » / « Tu serres les dents. Tu ne réponds pas. »
19 · noir + « 18 MINUTES PLUS TARD » · HUD accéléré 05:33→05:51 et 29:40→11:58 · NARRATEUR : « Tu tiens Karim. » / « Tu ne réponds pas. » / « Dix-huit minutes. »
20 · I14 · 05:51 / 11:58 · battement de cœur discret · NARRATEUR : « Mais il avance toujours. » / « L'eau lui arrive à la poitrine. »
21 · I15 · 05:53 / saute à 09:30 · FAUSSE MIMA (derrière les roseaux) : « Mon fils… je suis tombée. » / « Viens m'aider. Vite. » / NARRATEUR : « La voix de Mima. » ⏸ « Mais Mima ne peut pas marcher. »
22 · I16 · 05:54 / saute à 08:44 · NARRATEUR : « Tu regardes ses pieds. » ⏸ CHOC + tremblement · « Des sabots. » · TAMPON « RÈGLE N°2 ✓ »
23 · V17 · 05:57 / saute à 05:02 (ROUGE, pulse) · cœur plus rapide, musique qui monte · NARRATEUR : « Karim a de l'eau jusqu'au cou. » / « Tu ne le tiens plus que par le col. »
24 · I18 · 05:59 / saute à 03:00 · NARRATEUR : « Le ciel commence à rosir. » / « Trois minutes. » / « Tu pourrais tenir. Peut-être. »
25 · I19 · 05:59 / saute à 02:41 · NARRATEUR : « Ou tu plantes le fer. » / « Elle fuira tout de suite. » ⏸ « Mais Mima l'a dit : celui qui la chasse… elle ne l'oublie jamais. »
26 · ÉCRAN DE CHOIX (sur I20) · HUD figé 02:41 · musique COUPÉE NET, seulement le tic du compte 3-2-1 · NARRATEUR : « Tu plantes le fer… ou tu tiens jusqu'au soleil ? »
27 · CARTE FINALE · 6 s · l'eau revient très doucement · fondu au noir final

Remarque : l'image I01 n'est utilisée qu'à travers V01 (et floutée pour la fiche). I04, I08, I09, I12, I17 sont remplacées par leurs clips V04, V08, V09, V12, V17.

=====================================================================
10. VÉRIFICATION (obligatoire avant de me dire que c'est fini)
=====================================================================
1. Durée entre 2 min 10 et 2 min 40, résolution 1080x1920, 30 i/s, son présent.
2. Extrais une image toutes les 4 s dans travail/controle/ et REGARDE-les une par une : image qui remplit l'écran, HUD lisible et cohérent, sous-titres lisibles et dans le cadre, mot-clé en jaune, cartes bien affichées, aucune image noire imprévue, aucun bras ou objet bizarre.
3. Compte à rebours cohérent : il ne remonte jamais, il saute aux bons moments, il défile à la seconde entre deux sauts.
4. Chaque plan bouge (zoom, particules, brume) : aucune image complètement immobile.
5. Son : aucune voix coupée, voix toujours compréhensible au-dessus du fond, pas de saturation, -14 LUFS (mesure avec ffmpeg ebur128).
6. Fais un tableau d'intérêt par tranche de 5 s (note de 1 à 5 avec la raison). Si une tranche est sous 4, corrige avant de me montrer.
7. Donne-moi un rapport court : durée, ce qui est fait, les sons fabriqués, ce que tu n'as pas pu faire, et le chemin de sortie/aicha_ep02_v1.mp4. Si tu travailles dans le cloud, pousse la vidéo dans le dépôt, dans la_veillee/ep02_aicha_kandicha/rendus/montage/, pour que je la récupère.

=====================================================================
11. ENSUITE
=====================================================================
Je regarde la vidéo sur mon téléphone et je te dis ce qui ne va pas. Tu notes chaque correction comme règle datée dans SUIVI.md, tu corriges, et tu exportes v2, v3… sans écraser les anciennes.
```

---

## Les fichiers utilisés par le montage
| Type | Fichiers | Où |
|---|---|---|
| 14 images fixes | I02, I03, I05, I06, I07, I10, I11, I13, I14, I15, I16, I18, I19, I20 (+ I01 floutée pour la fiche) | [`rendus/images/`](rendus/images/) |
| 6 clips animés | V01, V04, V08, V09, V12, V17 | [`rendus/clips/`](rendus/clips/) |
| Voix | générées par Claude Code (edge-tts, gratuit) | — |
| Sons | fabriqués par Claude Code, ou tes fichiers Pixabay dans `sources/sons/` | — |
