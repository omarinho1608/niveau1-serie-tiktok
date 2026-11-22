# 🎬 PROMPT DE MONTAGE COMPLET – La Roue, épisode 01 « Le Bonhomme Sept-Heures »

⬅️ [Retour au script](script.md) · 🎞️ [Clips générés](rendus/)

> **Tout est dedans** : fichiers, script mot pour mot avec le minutage, la roue, le HUD, les choix, « TU ES MORT », le retour en arrière, la carte VRAI, les voix, les bruitages, la musique, l'export et la vérification.
> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code** (sur ton ordinateur ou dans le cloud). Il récupère lui-même les 17 clips sur GitHub.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel.
Règles : travaille toujours sur une copie (les originaux restent intacts), vérifie toi-même le résultat avant de me dire que c'est fini, ne publie jamais rien sans moi.

Objectif : une vidéo TikTok d'horreur « POV » de ~80 secondes, la plus CLEAN possible, pour un public de 16-25 ans. Rien d'enfantin : ambiance sombre, tendue, sound design de film d'horreur, rythme rapide, et le spectateur doit rester jusqu'au bout.
Style visé : les vidéos d'horreur « POV avec roulette + choix + tu meurs + on revient en arrière » qui marchent sur TikTok, mais avec NOTRE identité : la roue s'appelle « LA ROUE », notre retour en arrière s'appelle « ◀◀ LA ROUE RECULE », notre couleur signature est le rouge sang #E0242B et le jaune moutarde #F2B33D (le sweat du héros).

=====================================================================
0. RÉCUPÉRER LES FICHIERS
=====================================================================
Clone le dépôt : git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok
Crée un dossier de travail montage_roue_ep01/ (EN DEHORS du dépôt) avec : sources/ (copie), travail/, sortie/.
Copie dans sources/ : la_roue/ep01_bonhomme_sept_heures/rendus/clips/V01.mp4 … V17.mp4
(17 clips Kling, 720p, 9:16, 5 s chacun, SANS son, illustrations vectorielles plates très sombres).
Lis aussi pour contexte : la_roue/ep01_bonhomme_sept_heures/script.md et la_roue/ep01_bonhomme_sept_heures/rendus/README.md (notes clip par clip).
Si un fichier manque, arrête-toi et dis-le-moi.
S'il existe un fichier SUIVI.md (mes règles de montage), relis-le et applique-le. Sinon crée-le avec les sections STYLE et VOIX ci-dessous. À chaque correction que je te donne, ajoute une règle datée dans SUIVI.md.

=====================================================================
1. OUTILS (gratuits)
=====================================================================
- ffmpeg (Windows : winget install Gyan.FFmpeg ; Mac : brew install ffmpeg ; Linux : apt install ffmpeg)
- Python 3 + paquets : edge-tts (voix), Pillow (roue, HUD, cartes), numpy, scipy (sons).
- Polices libres Google Fonts, téléchargées dans travail/polices/ : « Montserrat » (ExtraBold et Black, pour les sous-titres et les boutons), « Bebas Neue » (HUD, titres), « JetBrains Mono » (heure du HUD).
- Si edge-tts n'arrive pas à se connecter et qu'il y a un proxy HTTPS dans l'environnement : --proxy "$HTTPS_PROXY".

=====================================================================
2. LA VIDÉO À OBTENIR
=====================================================================
1080x1920, 30 i/s, H.264 (CRF 17, preset slow, yuv420p, profil high) + AAC 48 kHz 192 kb/s. Durée 75 à 85 s (jamais moins de 62 s).
Fichier final : sortie/roue_ep01_bonhomme_v1.mp4 (versions suivantes : v2, v3… sans jamais écraser).
Export aussi : sortie/couverture.png (1080x1920) = image de V07 au moment où la bouche est la plus visible + le titre « LE BONHOMME SEPT-HEURES » en Bebas Neue blanc, un mot en rouge, ombre portée.

=====================================================================
3. STYLE VISUEL (le plus important)
=====================================================================
- TOUT EST EN CLIPS ANIMÉS : aucune image figée qui reste à l'écran. Chaque plan dure 2,5 à 4 s. Jamais plus de 2 s sans changement visible (nouveau plan, texte, HUD qui saute, zoom-coup).
- Mise à l'échelle : chaque clip est agrandi pour REMPLIR 1080x1920 (scale + crop au centre, lanczos), jamais de bandes noires.
- Mouvement de caméra ajouté sur chaque clip : zoom avant très lent 100 % → 104 % (fluide, sans saccade). Sur les plans de tension (V04, V10, V11, V15) : 100 % → 108 %.
- Si un plan doit durer plus longtemps que la partie utilisable d'un clip : ralentis à 0,8x maximum avec interpolation (minterpolate mi_mode=blend), ne fige jamais.
- Couches sur TOUTE la vidéo (c'est ce qui fait « clean et pro ») :
  · grain de film fin animé (opacité 6-8 %) ;
  · vignettage doux ;
  · très légère aberration chromatique sur les bords (1-2 px) ;
  · petites particules de poussière qui flottent (opacité 15 %), générées par toi.
  Ne change PAS les couleurs des clips (ils sont déjà bleu nuit).
- Transitions : COUPES SÈCHES presque partout (rythme TikTok). Fondu au noir 0,15 s seulement avant les morts. « Whip » flou (flou de mouvement vertical 0,12 s) quand on revient au choix après un retour en arrière.
- Chocs (jump scares, « TU ES MORT ») : zoom-coup 100 → 112 % en 0,1 s + tremblement d'image 0,3 s + flash blanc 2 images + glitch RVB 0,2 s.
- ZONES SÛRES TikTok : aucun texte important dans les 320 px du bas, ni dans les 140 px de droite (boutons TikTok), ni dans les 150 px du haut.

=====================================================================
4. LA ROUE (à dessiner toi-même avec Pillow, design 100 % à nous)
=====================================================================
- Fond : V01 très flouté (gaussien 25 px) et assombri à 35 %, avec le grain.
- Une roue de 900 px de diamètre au centre, 8 cases alternées noir #121218 et rouge sombre #5A0F14, fines séparations rouge #E0242B, un cercle central noir avec « LA ROUE » en Bebas Neue blanc.
- Dans chaque case, le nom d'une légende en Bebas Neue blanc (texte orienté vers le centre) : BONHOMME SEPT-HEURES · DAME BLANCHE · BÊTE DU GÉVAUDAN · LOUP-GAROU · CHASSE-GALERIE · LAVANDIÈRES · AÏCHA KANDICHA · ANKOU.
- Un pointeur rouge en haut, qui « claque » à chaque case qui passe (il bascule de 8° puis revient).
- Animation : la roue est DÉJÀ en train de tourner vite à la première image (pas d'intro lente), décélère (courbe ease-out cubique) et s'arrête pile sur BONHOMME SEPT-HEURES au mot « Bonhomme ». Petit rebond arrière de 3° à l'arrêt.
- À l'arrêt : la case gagnante s'illumine en rouge vif, flash, puis le nom « LE BONHOMME SEPT-HEURES » s'écrase au centre de l'écran (Bebas Neue 150 px blanc, « SEPT-HEURES » en rouge, échelle 140 → 100 % en 0,12 s) avec un gros impact sonore, puis « QUÉBEC 🇨🇦 » en petit dessous (dessine le drapeau si l'emoji ne s'affiche pas).
- Son : cliquet mécanique synchronisé sur chaque case qui passe (les clics ralentissent avec la roue).
- Garde ce générateur de roue dans un script réutilisable (travail/roue.py, paramètre = nom de la légende gagnante) : il servira à chaque épisode.

=====================================================================
5. LE HUD (en haut, à partir du plan 3, sauf sur la roue et la carte VRAI)
=====================================================================
- En haut à gauche (marge 60 px, sous les 150 px de sécurité) : une petite pastille rouge qui clignote (comme « REC ») + « BONHOMME SEPT-HEURES · TROIS-RIVIÈRES » en Bebas Neue 46 px blanc.
- Juste en dessous : l'heure en gros, JetBrains Mono Bold 78 px blanc : « 18:58:00 ». Elle DÉFILE À LA SECONDE (1 s de vidéo = 1 s en plus) et SAUTE aux valeurs du script (glitch 0,15 s + petit « tic »).
- À partir de 19:00:00 : l'heure devient ROUGE #E0242B et pulse légèrement (100 → 104 % chaque seconde).
- Léger dégradé noir en haut de l'écran (noir 45 % → transparent sur 300 px) pour que le HUD soit toujours lisible.

=====================================================================
6. SOUS-TITRES
=====================================================================
- Mot à mot, groupes de 1 à 3 mots, synchronisés sur le minutage des mots d'edge-tts (WordBoundary). Jamais en retard sur la voix.
- Centrés, à 64 % de la hauteur. Montserrat Black 84 px, MAJUSCULES, blanc, contour noir fin 5 px + ombre douce.
- UN mot-clé par phrase en ROUGE #E0242B (le plus fort : « sept heures », « Léa », « trois fois », « en avance », « mort », « pile », « toute seule », « vide »…).
- Apparition : pop 85 % → 100 % en 0,07 s. Pas de sous-titres pendant la roue (le nom s'écrase en gros à la place) ni sur la carte VRAI.
- Répliques de LÉA : jaune moutarde #F2B33D. Répliques du BONHOMME : rouge, en italique, légèrement tremblées.

=====================================================================
7. VOIX (edge-tts ; une réplique = un fichier dans travail/voix/)
=====================================================================
NARRATEUR : voix neutre mais HUMAINE, ton dynamique, un peu stressé, au « tu », au présent. Pas un robot qui lit, pas un conteur pour enfants.
- Voix : fr-FR-RemyMultilingualNeural (la plus naturelle). Si elle n'existe pas : fr-FR-HenriNeural.
- Débit de base rate +8 %. Phrases d'action (plans 10, 11, choix) : rate +14 %. Phrases de suspense (plans 7, 12, 17, 19) : rate -4 % et volume un peu plus bas.
- Pour que ça sonne humain et pas monotone :
  · génère chaque PHRASE séparément et fais varier légèrement le pitch d'une phrase à l'autre (entre -3 Hz et +2 Hz) ;
  · garde les « … » du script : ce sont des respirations ;
  · ajoute une petite inspiration (bruit de souffle très court et discret, -30 dB) avant 4 ou 5 phrases clés (avant « On frappe », « Il est en avance », « Sept heures. Pile », « Au matin… ») ;
  · traitement : passe-haut 80 Hz, légère présence +2 dB à 3 kHz, compression douce (ratio 3:1), toute petite réverbération de pièce (aecho=0.8:0.6:25:0.12) pour qu'elle ne sonne pas « collée » ;
  · 0,25 s de silence entre deux phrases, 0,9 s quand le script indique ⏸.
- LÉA (petite fille de 6 ans, capricieuse au début) : fr-FR-EloiseNeural (voix d'enfant), rate +5 %, pitch +2 Hz.
- LE BONHOMME (« Qui ne dort pas ? ») : fr-FR-HenriNeural, rate -30 %, pitch -25 Hz, puis ffmpeg : abaisse encore la voix (asetrate à 0,85 + aresample), ajoute un chuchotement (le même texte en voix normale passé en bruit filtré), réverbération longue, et superpose une 2e copie décalée de 30 ms et un demi-ton plus bas. Elle doit faire froid dans le dos, pas rire.
- Les voix passent toujours au-dessus du fond : ducking de l'ambiance et de la musique de -9 dB pendant qu'on parle.

=====================================================================
8. BRUITAGES ET MUSIQUE (l'atmosphère)
=====================================================================
Si sources/sons/ contient des fichiers, utilise-les en priorité. Je peux en télécharger de vrais gratuitement sur pixabay.com/fr/sound-effects (dis-moi lesquels te manquent). Noms attendus :
cliquet_roue, impact_grave, whoosh, riser, tictac, toc_porte, grincement_porte, sac_traine, souffle_rauque, ronflement, ding_reveil, vent_neige, tv_dessin_anime, drone, battement_coeur, rewind_cassette, glitch, oiseaux_matin.
Sinon FABRIQUE-LES avec Python/ffmpeg (et dis-moi lesquels sont fabriqués) :
- Ambiance de fond : vent d'hiver (bruit rose filtré passe-bas ~600 Hz, modulé lentement) très bas (-32 dB), continu, sauf pendant les silences totaux.
- Musique : PAS de musique joyeuse. Un DRONE sombre (2-3 sinusoïdes graves 40-60 Hz légèrement désaccordées + bruit filtré + une note aiguë lointaine qui vibre) qui monte doucement de -28 dB à -18 dB entre les plans 3 et 8, puis repart plus bas après le retour en arrière, et remonte jusqu'au plan 17.
- RISER (montée de tension, 2 s) avant chaque choix et avant chaque jump scare, suivi d'un SILENCE TOTAL de 0,5 s, puis du choc. C'est ce contraste qui fait sursauter.
- Impact grave (« boum » cinématique : sinus 45 Hz qui descend + bruit court + réverbération) : nom qui s'écrase sur la roue, « TU ES MORT », jump scares.
- Plan 3 : son de dessin animé lointain venant de la télé (mélodie jouet très étouffée, passe-bas), qui S'ARRÊTE NET au plan 5 (les coups).
- Tic-tac fort (plan 4), 3 coups lents et lourds sur une porte (plan 5), grincement de porte + sac qu'on traîne sur le plancher (plan 12), souffle rauque (plan 17), « ding » de réveil (plan 11), faux ronflement puis silence (plan 15), oiseaux du matin très doux (plan 18 : contraste après la nuit).
- Battement de cœur discret à partir du plan 13, qui accélère jusqu'au plan 17.
- Rewind : bruit de cassette qu'on rembobine (bruit filtré dont la hauteur monte) + voix inversée accélérée pendant « ◀◀ LA ROUE RECULE ».
- Mixage final normalisé à -14 LUFS intégrés, crête max -1 dBTP. Les impacts doivent être puissants mais ne jamais saturer.

=====================================================================
9. ÉCRANS SPÉCIAUX (Pillow, 1080x1920)
=====================================================================
- ÉCRAN DE CHOIX : le clip continue derrière (ralenti 0,8x et assombri à 55 %). En haut : « TU FAIS QUOI ? » (Montserrat Black 92 px blanc). Deux gros boutons arrondis pleine largeur (marges 90 px), fond noir 75 % avec bord blanc 4 px : « 1 · TU BLOQUES LA PORTE » et « 2 · TU COUCHES LÉA » (Montserrat ExtraBold 58 px blanc, le chiffre dans une pastille rouge). Les boutons arrivent l'un après l'autre (glisse depuis la gauche, 0,15 s). Un anneau de compte à rebours rouge se vide en 2 s avec un « tic » par demi-seconde. Puis le bouton choisi s'allume (fond rouge #E0242B, petit zoom 100 → 105 %) avec un clic, l'autre s'éteint.
- « TU ES MORT. » : flash blanc 2 images, puis écran figé teinté rouge (l'image du choc, désaturée, rouge multiplié) + glitch, « TU ES MORT. » en Bebas Neue 190 px blanc qui tremble, au centre. En dessous, la leçon en Montserrat ExtraBold 50 px (ex. « IL NE PASSE JAMAIS PAR LA PORTE. »). Durée 1,8 s. Ce plan peut être figé, c'est le seul.
- « ◀◀ LA ROUE RECULE » : les derniers plans défilent À L'ENVERS en accéléré (x4) avec des lignes de VHS, un léger décalage RVB et le texte « ◀◀ LA ROUE RECULE » en haut au centre (Bebas Neue 90 px blanc, le « ◀◀ » rouge qui clignote) + une petite roue qui tourne à l'envers dans le coin. Durée 1,5 s (1,2 s pour le 2e).
- CARTE « VRAI » : fond = V01 flouté et assombri 30 %. Une carte noire arrondie au centre (bord rouge 3 px), en haut une étiquette verte #3BB273 « ✓ VRAI » (Bebas Neue 90 px), puis le texte en blanc (Montserrat SemiBold 46 px, centré, interligne 1,35) : « Le Bonhomme Sept-Heures est un personnage du folklore québécois, utilisé pour que les enfants aillent se coucher tôt. Son nom viendrait de l'anglais "bone-setter" : le rebouteux. » La carte glisse depuis le bas en 0,25 s. Le narrateur la lit. En petit en bas : « Source : folklore du Québec ».
- FIN : sur V17, la question « ET TOI, TU TE COUCHES À QUELLE HEURE ? 👇 » (Montserrat Black 70 px, blanc, « QUELLE HEURE » en rouge) apparaît mot par mot. Puis, 0,4 s avant la fin, la roue réapparaît en fondu et recommence à tourner, avec le premier clic de cliquet → la vidéo se reboucle parfaitement sur son début.

=====================================================================
10. SCRIPT COMPLET AVEC MINUTAGE (≈ 80 s)
=====================================================================
Format : n° · temps visé · visuel (partie du clip à utiliser) · HUD · voix / sons. ⏸ = 0,9 s de silence. Le minutage exact s'adapte à la durée réelle des voix.

0 · 0,0–0,6 s · ACCROCHE : la dernière seconde de V07 (les doigts sur la tête du héros), zoom-coup + glitch · pas de HUD · impact grave + souffle. (C'est un teaser de ce qui va arriver : il doit choquer dès la première image.)
1 · 0,6–4,5 s · LA ROUE (section 4) · pas de HUD · cliquet · NARRATEUR : « La roue tourne… et ce soir, tu devras faire face au… » → la roue s'arrête → « Bonhomme Sept-Heures. » + impact, le nom s'écrase.
2 · 4,5–8,5 s · V01 (0–4 s) · pas de HUD · vent · NARRATEUR : « Au Québec, à sept heures, les enfants doivent être couchés. » / « Sinon… le Bonhomme Sept-Heures vient les chercher. » · Au milieu du plan, une étiquette rouge s'affiche en haut : « RÈGLE : À 19:00, TOUT LE MONDE DORT. » (Bebas Neue 64 px, fond rouge, glisse depuis la gauche).
3 · 8,5–12,5 s · V02 (0–4 s) · HUD apparaît : 18:58:00 · télé lointaine · NARRATEUR : « Tu gardes ta petite sœur, Léa. » / « Il est six heures cinquante-huit. Elle refuse d'aller se coucher. » / LÉA : « Encore un dessin animé ! »
4 · 12,5–15 s · V03 (0–2,5 s) · saute à 18:59:00 · TIC-TAC très fort, la télé continue · pas de voix.
5 · 15–18,5 s · V04 (0,5–4 s) · 18:59:05 · la télé S'ARRÊTE NET · 3 COUPS lents · NARRATEUR (bas) : « On frappe. » ⏸ « Trois fois. »
6 · 18,5–23,5 s · V05 (0–3 s puis ralenti) · 18:59:12 · riser · NARRATEUR : « Il est en avance. » → ÉCRAN DE CHOIX 1 : « 1 · TU BLOQUES LA PORTE » / « 2 · TU COUCHES LÉA » → le 1 s'allume.
7 · 23,5–27 s · V06 (0–3,5 s) · 18:59:20 · NARRATEUR : « Tu bloques la porte avec ton dos. » ⏸ (silence total sauf le cœur, 0,6 s)
8 · 27–30,5 s · V07 (0–3,5 s : il est derrière toi, la bouche s'ouvre, les doigts se posent sur ta tête) · 18:59:24 · le choc tombe pile quand les doigts touchent la tête : impact + flash → « TU ES MORT. » / leçon « IL NE PASSE JAMAIS PAR LA PORTE. » · NARRATEUR : « Il ne passe jamais par la porte. »
9 · 30,5–38 s · « ◀◀ LA ROUE RECULE » (V07 → V06 → V05 à l'envers, x4, 1,5 s) puis CARTE VRAI (≈ 6 s) · NARRATEUR : « Vrai. » / « Le Bonhomme Sept-Heures vient du folklore québécois. » / « Son nom viendrait de l'anglais bone-setter… le rebouteux. »
10 · 38–39 s · retour rapide sur l'ÉCRAN DE CHOIX 1 (whip), cette fois le 2 s'allume · clic.
11 · 39–42,5 s · V08 (0–3,5 s) · saute à 18:59:40 · pas rapides dans l'escalier · NARRATEUR (rapide) : « Tu attrapes Léa. » / « Tu montes les marches deux par deux. »
12 · 42,5–46 s · V09 (0–3,5 s) · 18:59:57 → 18:59:58 → 18:59:59 → 19:00:00 (passe au ROUGE au « ding ») · DING du réveil · NARRATEUR : « Sept heures. » ⏸ « Pile. »
13 · 46–49,5 s · V10 (0–3,5 s) · 19:00:06 · grincement long, puis un SAC QU'ON TRAÎNE sur le plancher · cœur qui commence · NARRATEUR (bas) : « La porte s'ouvre. » / « Toute seule. »
14 · 49,5–53 s · V11 (0–3,5 s) · 19:00:13 · le sac traîne · BONHOMME (chuchoté, déformé) : « Qui… ne dort pas ? »
15 · 53–57,5 s · V12 (0–4 s) · 19:00:19 · sanglots étouffés · NARRATEUR : « Léa sanglote. » → riser → ÉCRAN DE CHOIX 2 : « 1 · TU FAIS SEMBLANT DE RONFLER » / « 2 · TU LUI COUVRES LA BOUCHE » → le 1 s'allume.
16 · 57,5–61 s · V13 (0–3 s SEULEMENT, la fin est floue) · 19:00:27 · faux ronflement… silence 0,5 s… impact → « TU ES MORT. » / « CEUX QUI DORMENT NE RONFLENT PAS POUR LUI. » · NARRATEUR : « Ceux qui dorment… ne ronflent pas pour lui. »
17 · 61–62,5 s · « ◀◀ LA ROUE RECULE » court (1,2 s) → ÉCRAN DE CHOIX 2, le 2 s'allume.
18 · 62,5–66 s · V14 (0–3,5 s) · 19:00:35 · cœur rapide, respiration retenue · NARRATEUR (chuchoté) : « Tu poses ta main sur sa bouche. » / « Vous ne respirez plus. »
19 · 66–70,5 s · V15 (0–4,5 s : il se penche, puis s'efface) · 19:00:41 · souffle rauque très proche, puis des pas qui s'éloignent · NARRATEUR : « Il se penche. » ⏸ « Longtemps. » / « Puis il s'en va. »
20 · 70,5–74 s · V16 (0–3,5 s) · le HUD saute à 07:12:00 (heure BLANCHE de nouveau) · tout le drone COUPE NET, oiseaux du matin, calme trompeur · NARRATEUR : « Au matin… » ⏸ « le lit de Léa est vide. »
21 · 74–80 s · V17 (0–5 s, ralenti à 0,85x si besoin) · le HUD affiche 19:04:00 en rouge qui clignote (c'était hier soir) · vent, sac qui traîne au loin · NARRATEUR (lent, presque chuchoté) : « Elle s'était relevée… » ⏸ « …pour finir son dessin animé. » → la question finale (section 9) → la roue revient et reboucle.

=====================================================================
11. VÉRIFICATION AVANT DE ME DIRE QUE C'EST FINI
=====================================================================
1. Exporte une planche de contrôle : une image toutes les 2 secondes, en mosaïque (sortie/controle_v1.jpg). Regarde-la toi-même : pas de bande noire, pas de texte coupé ou hors des zones sûres, pas de HUD sur la roue ni sur la carte VRAI, la roue s'arrête bien sur BONHOMME SEPT-HEURES.
2. Vérifie que la voix et les sous-titres sont synchronisés (extrais 3 passages de 3 s et compare le minutage des mots).
3. Mesure le son (ffmpeg ebur128) : -14 LUFS ±1, crête ≤ -1 dBTP. Vérifie qu'aucune voix n'est couverte par les bruitages.
4. Vérifie la durée (75-85 s), 1080x1920, 30 i/s.
5. Vérifie que chaque plan dure entre 2,5 et 4,5 s, sauf les écrans spéciaux.
6. Puis fais-moi un résumé simple : ce qui est fait, les sons fabriqués ou téléchargés, et ce que tu me conseilles de regarder en premier. Ne publie rien.
```

---

## 💡 Après le premier rendu
Regarde-le **sur ton téléphone, le son allumé**, puis donne tes corrections en une phrase (« la voix est trop lente », « le choc arrive trop tard », « le texte est trop petit »…). Claude les note dans `SUIVI.md` et ne refera plus l'erreur aux épisodes suivants.
