> ⚠️ **Version remplacée.** Utilise plutôt le [🎬 **PROMPT DE MONTAGE COMPLET**](PROMPT_MONTAGE_COMPLET.md) : il récupère tout seul les images et les clips sur GitHub et contient tout (voix, effets, sons, cartes, vérification).

# 🎬 Prompt de montage pour Claude Code – La Veillée, épisode 02 « Aïcha Kandicha » · FORMAT V2

⬅️ [Retour à la série](../README.md) · 📝 [Script](script.md) · ▶️ [Prompts Kling](PROMPTS_A_COLLER.md)

## Avant de lancer
1. Dans ton dossier de montage habituel (celui qui contient ton `SUIVI.md`), crée **`ep02_aicha_v2`**.
2. **Les images et les clips sont déjà générés** : télécharge les dossiers **`images`** (`I01.png` à `I20.png`) et **`clips`** (`V01`, `V04`, `V08`, `V09`, `V12`, `V17` .mp4) depuis [`rendus/`](rendus/) dans ce dépôt GitHub, et mets-les dans `ep02_aicha_v2`. Ou plus simple : dis à Claude Code de cloner le dépôt `omarinho1608/niveau1-serie-tiktok` (branche `claude/pensive-ramanujan-14exqk`) et de copier `la_veillee/ep02_aicha_kandicha/rendus/images` et `rendus/clips` dans `ep02_aicha_v2/`.
3. *(Optionnel)* **`sons`** : `eau.mp3`, `grenouilles.mp3`, `pas.mp3`, `coeur.mp3`, `musique.mp3` (drone sombre), `choc.mp3`.
4. Ouvre ta session Claude Code **dans le dossier de montage habituel** et colle le bloc ci-dessous.

---

```text
Nouvel épisode à monter, dans un NOUVEAU STYLE : La Veillée, épisode 02 « Aïcha Kandicha », format V2. Fichiers dans ep02_aicha_v2/ (images/I01.png à I20.png, clips/V01, V04, V08, V09, V12, V17 .mp4, sons/ optionnel). Travaille dans ep02_aicha_v2/ (travail/ et sortie/), sur des copies, sans modifier les originaux. Ne publie rien.

AVANT TOUT : relis SUIVI.md. Les règles « captivant » et de qualité restent valables. ATTENTION, le style visuel change : on quitte le pixel art pour de l'illustration vectorielle plate façon motion design. Les règles de SUIVI.md qui concernent le pixel art ne s'appliquent plus. Ajoute à SUIVI.md une section datée « FORMAT V2 » avec les règles ci-dessous.

OBJECTIF
Vidéo TikTok 1080x1920, 30 i/s, environ 2 min 25 (entre 2 min 10 et 2 min 40). Partie 1, qui finit sur un choix A/B.

LE STYLE D'ANIMATION (le plus important)
La plupart des plans sont des IMAGES FIXES : c'est toi qui les fais vivre, comme dans les vidéos de récit animé vectoriel sur TikTok.
- Chaque image fixe a un zoom avant lent et régulier (100 % → 106 % sur la durée du plan). Varie le point de zoom : visage, mains, objet important.
- Parallaxe légère quand c'est possible : si tu peux séparer le personnage du fond (détourage avec rembg, gratuit), fais bouger le fond un peu moins vite que le personnage. Sinon, zoom simple.
- Respiration : sur les gros plans de visage, une très légère oscillation d'échelle (±0,6 % toutes les 3 s), pour que le personnage ait l'air vivant.
- Particules en continu : de fines particules de poussière / brume claires qui flottent lentement vers le haut sur toute la vidéo (calque généré par toi, opacité 25 à 35 %).
- Lumière vivante : léger scintillement (±4 % de luminosité, irrégulier) sur les plans où il y a une lampe à huile (I04, I05, I15, I16).
- Brume : un calque de brume qui glisse lentement de gauche à droite sur les plans de l'oued (I01, I07 à I20).
- Transitions : FONDUS ENCHAÎNÉS de 0,4 s entre les plans calmes (effet souvenir, fluide). COUPES SÈCHES + tremblement de 0,3 s sur les chocs (plans 16, 17, 22).
- Les 6 clips animés (V01, V04, V08, V09, V12, V17) remplacent l'image du même numéro. Coupe-les ou ralentis-les (max 0,8x) pour coller à la voix.
- Jamais plus de 2,5 s sans changement à l'écran (nouvelle image, zoom de point, texte, HUD qui saute).

LE HUD (en haut, pendant toute la vidéo, sauf sur les cartes plein écran)
- À gauche : drapeau 🇲🇦 dessiné simplement + l'heure réelle en blanc (05:21…), police condensée.
- À droite : un encadré noir à bord rouge avec « ☀ SOLEIL » en petit et un compte à rebours en gros chiffres blancs (42:00) qui DÉFILE À LA SECONDE pendant la vidéo.
- Le compte à rebours et l'heure SAUTENT aux moments indiqués dans le SCRIPT (petit glitch de 0,2 s + bruit de « tic » quand ça saute). Entre deux sauts, il défile normalement seconde par seconde.
- Au plan 19 (« 18 MINUTES PLUS TARD ») : les chiffres défilent en accéléré de 29:40 à 11:58 en 2 s.
- Du plan 23 au plan 25, le compte à rebours passe en ROUGE et pulse légèrement. Au plan 26, il se FIGE.

SOUS-TITRES
Mot à mot (1 à 3 mots), centrés, à 62 % de la hauteur. Police condensée très grasse (Bebas Neue ou Oswald Bold, libres), blanche, ombre douce, sans contour épais. Un mot-clé par phrase en JAUNE MOUTARDE (#F2B33D), la couleur du sweat du héros, notre signature.

VOIX (edge-tts)
- NARRATEUR (au « tu », présent, tendu, rapide pendant l'action, lent pendant les silences) : la même voix que d'habitude dans SUIVI.md.
- MIMA (vieille grand-mère, douce, terrifiée) : fr-FR-VivienneMultilingualNeural (sinon fr-FR-DeniseNeural), rate -15 %, pitch -6Hz.
- KARIM (ado de 17 ans, voix vide, en transe) : une voix masculine française différente du narrateur, rate -20 %, monotone.
- AÏCHA (douce, envoûtante) : fr-FR-DeniseNeural, rate -25 %, réverbération, léger écho. Les chuchotements « à l'oreille » : volume bas, très proche, stéréo d'un seul côté.
- LA FAUSSE MIMA (plan 21) : la voix de Mima + le traitement d'Aïcha (réverbération, écho), un peu plus grave.
- Le prénom chuchoté au plan 18 : utilise « Ilyas ».

CARTES (vectorielles, plates, même style)
- FICHE (plan 5) : fond flouté de I01. « AÏCHA KANDICHA » très gros en blanc, « [ RÉGION DE MEKNÈS · MAROC ] » en rouge, jauge NIVEAU DE DANGER pleine → « MORTEL », en petit : « ELLE APPELLE LES HOMMES PAR LEUR PRÉNOM. ELLE REPART AU LEVER DU SOLEIL. »
- RÈGLES (plans 7 à 10) : plein écran noir, une étiquette rouge vif « RÈGLE N°1 » (2, 3, 4) en haut, le texte de la règle en blanc, police condensée. Maximum 3 à 4 s chacune.
- TAMPONS : « RÈGLE N°1 ✗ » rouge au plan 14 ; « RÈGLE N°2 ✓ » vert au plan 22. Ils s'écrasent en haut à droite pendant 1,5 s avec un bruit sourd.
- « 18 MINUTES PLUS TARD » (plan 19) : texte blanc sur fond noir, pendant que le HUD défile en accéléré.
- ÉCRAN DE CHOIX (plan 26) : fond I20 flouté et assombri. En haut, « TU FAIS QUOI ? » en très gros. Deux boutons ronds : orange « JE PLANTE LE FER » et bleu « JE TIENS JUSQU'AU SOLEIL ». En dessous, un compte à rebours circulaire 3 → 2 → 1 (cercle rouge qui se vide). En bas : « Vote en commentaire · PARTIE 2 bientôt ».
- CARTE FINALE (plan 27) : « D'OÙ VIENT LA LÉGENDE » + le texte du script.md (section « Carte »).

SON
Ambiance continue (eau, brume, vent léger). Les grenouilles et les chiens au début, qui s'ARRÊTENT net au plan 12. Battement de cœur discret qui accélère à partir du plan 20. Musique drone sombre qui monte doucement du plan 13 au plan 25, puis coupure NETTE au plan 26 (silence + juste le tic du compte à rebours circulaire). Normalisation -14 LUFS.

SCRIPT : lis le tableau complet du fichier ep02_aicha_v2/script.md si je l'y ai copié. Sinon, utilise celui-ci (plan · image · HUD · voix/son) :
1 · V01 · 05:21 · SOLEIL 42:00 · eau · NARRATEUR : « Il est 5 h 21. » / « Quelqu'un appelle ton cousin par son prénom. » / « Depuis l'oued. »
2 · I02 · 05:21 · AÏCHA (douce, lointaine) : « Kariiim… »
3 · I03 · 05:22 · 41:02 · NARRATEUR : « Tu es en vacances chez ta grand-mère, près de Meknès. » / « Le lit de Karim est vide. La fenêtre est ouverte. »
4 · V04 · 05:22 · NARRATEUR : « Mima est déjà réveillée. » / « Ses mains tremblent. » / MIMA : « Elle est revenue. »
5 · FICHE · NARRATEUR : « Aïcha Kandicha. »
6 · I05 · 05:23 · 40:15 · MIMA : « Mes jambes ne me portent plus. C'est toi qui vas y aller. » / « Écoute-moi bien. »
7 · RÈGLE N°1 · MIMA : « Ne réponds jamais à ton prénom. »
8 · RÈGLE N°2 · MIMA : « Si tu doutes… regarde ses pieds. »
9 · RÈGLE N°3 · MIMA : « Le fer la fait fuir. Mais celui qui la chasse… elle ne l'oublie jamais. »
10 · RÈGLE N°4 · MIMA : « Au lever du soleil, elle doit rentrer dans l'eau. Tiens jusque-là. »
11 · I06 · 05:25 · 37:48 · pas rapides, souffle · NARRATEUR : « Tu cours. » / « Le chemin vers l'oued fait huit cents mètres. » / « Tu ne l'as jamais trouvé aussi long. »
12 · I07 · 05:29 · 33:30 · les grenouilles s'arrêtent net · NARRATEUR : « D'un coup, les grenouilles se taisent. » / « Même les chiens du village. » ⏸ « Plus rien ne bouge. »
13 · V08 · 05:30 · NARRATEUR : « Karim est dans l'eau. Jusqu'aux genoux. » / « Il avance. » / « Il ne cligne pas des yeux. »
14 · V09 · 05:30 · 32:05 · AÏCHA : « Kariiim… viens. » / KARIM (absent) : « …J'arrive. » · TAMPON « RÈGLE N°1 ✗ »
15 · I10 · 05:31 · NARRATEUR : « Tu l'attrapes par le bras. » / « Il te repousse. » / « Il est deux fois plus fort que d'habitude. »
16 · I11 · 05:32 · 30:11 · NARRATEUR : « Tu fais ce que Mima a dit. » / « Tu regardes ses pieds. » ⏸ choc · « Des sabots. »
17 · V12 · 05:32 · silence total · NARRATEUR : « Elle a vu que tu avais vu. »
18 · I13 · 05:33 · 29:40 · AÏCHA (chuchoté à l'oreille) : « Ilyas… » / NARRATEUR : « Maintenant, c'est ton prénom qu'elle chuchote. » / « Tu serres les dents. Tu ne réponds pas. »
19 · noir + « 18 MINUTES PLUS TARD » · HUD accéléré 05:33→05:51 et 29:40→11:58 · NARRATEUR : « Tu tiens Karim. » / « Tu ne réponds pas. » / « Dix-huit minutes. »
20 · I14 · 05:51 · 11:58 · NARRATEUR : « Mais il avance toujours. » / « L'eau lui arrive à la poitrine. »
21 · I15 · 05:53 · 09:30 · FAUSSE MIMA : « Mon fils… je suis tombée. » / « Viens m'aider. Vite. » / NARRATEUR : « La voix de Mima. » ⏸ « Mais Mima ne peut pas marcher. »
22 · I16 · 05:54 · 08:44 · NARRATEUR : « Tu regardes ses pieds. » ⏸ « Des sabots. » · TAMPON « RÈGLE N°2 ✓ »
23 · V17 · 05:57 · 05:02 (rouge) · cœur, musique qui monte · NARRATEUR : « Karim a de l'eau jusqu'au cou. » / « Tu ne le tiens plus que par le col. »
24 · I18 · 05:59 · 03:00 · NARRATEUR : « Le ciel commence à rosir. » / « Trois minutes. » / « Tu pourrais tenir. Peut-être. »
25 · I19 · 05:59 · 02:41 · NARRATEUR : « Ou tu plantes le fer. » / « Elle fuira tout de suite. » ⏸ « Mais Mima l'a dit : celui qui la chasse… elle ne l'oublie jamais. »
26 · ÉCRAN DE CHOIX sur I20 · HUD figé 02:41 · coupure de la musique · NARRATEUR : « Tu plantes le fer… ou tu tiens jusqu'au soleil ? »
27 · CARTE FINALE · 6 s · l'eau qui coule

VÉRIFICATION (comme d'habitude, plus) :
- Le compte à rebours est cohérent : il ne remonte jamais, il saute aux bons moments, il défile à la seconde entre deux sauts.
- Chaque image fixe bouge (zoom, particules, brume) : aucune image complètement immobile.
- Images de contrôle toutes les 5 s (regarde-les), tableau d'intérêt par tranche de 5 s (aucune sous 4/5), durée, -14 LUFS.
- Rapport court + chemin de ep02_aicha_v2/sortie/aicha_ep02_v2.mp4.
```
