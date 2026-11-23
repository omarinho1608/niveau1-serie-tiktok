# 🎬 PROMPT DE MONTAGE COMPLET – Thread horreur, épisode 01 « Les 5 règles »

⬅️ [Retour au script](script.md) · 🎞️ [Clips générés](rendus/)

> **Tout est dedans** : fichiers, script mot pour mot, voix, SMS, sons, musique, coupes des clips, export et vérification.
> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code**. Il récupère lui-même les 21 clips sur GitHub.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel.
Règles : travaille toujours sur une copie (les originaux restent intacts), vérifie toi-même le résultat avant de me dire que c'est fini, ne publie jamais rien sans moi.

OBJECTIF : un « thread horreur » TikTok d'environ 2 minutes (1 min 55 à 2 min 15), pour un public de 16-25 ans. Rien d'enfantin.
Les 3 priorités, dans l'ordre :
1. LE SPECTATEUR RESTE JUSQU'AU BOUT : accroche dans la 1re seconde, tension qui monte sans arrêt, chaque plan donne une nouvelle info ou une nouvelle peur.
2. L'HISTOIRE COULE SANS ÊTRE INTERROMPUE : la voix de la narratrice ne s'arrête jamais longtemps, les SMS et les textes apparaissent PAR-DESSUS les clips (jamais un écran figé qui coupe l'histoire), pas de carte plein écran sauf la liste des règles (courte) et le SMS final.
3. UNE AMBIANCE QUI FAIT VRAIMENT PEUR : sons de maison la nuit, silences avant les chocs, sound design de film d'horreur.

=====================================================================
0. RÉCUPÉRER LES FICHIERS
=====================================================================
git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok
Crée un dossier de travail montage_thread_ep01/ (EN DEHORS du dépôt) avec : sources/ (copie), travail/, sortie/.
Copie dans sources/ : thread_horreur/ep01_les_cinq_regles/rendus/clips/V01.mp4 … V21.mp4 (21 clips Kling, 720p, 9:16, 5 s, SANS son, vectoriel plat très sombre).
Lis pour contexte : thread_horreur/ep01_les_cinq_regles/script.md et rendus/README.md.
S'il existe SUIVI.md (mes règles de montage), applique-le. Sinon crée-le. Chaque correction que je te donne = une règle datée dans SUIVI.md.

=====================================================================
1. OUTILS (gratuits)
=====================================================================
ffmpeg ; Python 3 + edge-tts, Pillow, numpy, scipy. Polices Google Fonts : « Montserrat » (Black, ExtraBold, SemiBold), « Inter » (bulles de SMS, comme un vrai téléphone), « JetBrains Mono » (heure).
Si edge-tts ne se connecte pas et qu'il y a un proxy : --proxy "$HTTPS_PROXY".

=====================================================================
2. EXPORT
=====================================================================
1080x1920, 30 i/s, H.264 CRF 17 preset slow yuv420p + AAC 48 kHz 192 kb/s. Fichier : sortie/thread_ep01_v1.mp4 (puis v2, v3… sans écraser).
Couverture : sortie/couverture.png = l'image de V19 où la bouche est la plus ouverte + le texte « 🧵 5 RÈGLES. J'EN AI ENFREINT UNE. » en Montserrat Black blanc, « UNE » en rouge.

=====================================================================
3. STYLE VISUEL
=====================================================================
- Tous les plans sont des clips animés. Chaque clip est agrandi pour remplir 1080x1920 (scale + crop centre, lanczos), jamais de bandes noires.
- Les clips sont très sombres : remonte légèrement les ombres (courbe douce, +8 % de luminosité dans les noirs) SANS changer les couleurs, pour que tout reste lisible sur téléphone.
- Zoom avant très lent sur chaque plan (100 → 104 %). Plans de tension (V06, V12, V13, V14, V15, V18) : 100 → 108 %.
- Couches sur toute la vidéo : grain de film fin (6 %), vignettage, petites poussières qui flottent (10 %).
- Transitions : COUPES SÈCHES (rythme TikTok). Sur les changements de lieu (cuisine → salon → étage → chambre → dehors) : fondu au noir très court (0,2 s) pour que le spectateur se repère.
- Chocs (plans 9, 17, 21, 22) : zoom-coup 100 → 112 % en 0,1 s + tremblement 0,3 s + glitch RVB 0,15 s.
- ZONES SÛRES TikTok : aucun texte important dans les 320 px du bas, les 140 px de droite ni les 150 px du haut.

COUPES DES CLIPS (j'ai vérifié chaque clip image par image ; certains ont un défaut en fin de clip, ne l'utilise JAMAIS) :
| Clip | Partie à utiliser | Pourquoi |
| V02 | 0 à 2,3 s (ralenti 0,8x si besoin) | des mains entrent par les bords après 2,4 s |
| V03 | 1,6 à 5 s | un flash de lumière vers 1,3 s |
| V05 | 0 à 4 s | Noé ferme les yeux à la fin |
| V06 | 0 à 3 s | une lampe apparaît au plafond ensuite |
| V12 | 0 à 4 s | des mains entrent par les coins à la fin |
| V13 | 0 à 4,5 s | |
| V15 | 0 à 2,5 s (ralenti 0,8x) | ensuite les cheveux tombent par terre comme une perruque (ridicule) |
| V21 | 0 à 4 s | des mains entrent par le bas à la fin |
| tous les autres | 0 à 5 s, coupe librement | OK sur toute la durée |
Si un plan doit durer plus longtemps que la partie utilisable : ralentis (max 0,8x, minterpolate blend), ne fige jamais l'image.

=====================================================================
4. LE TÉLÉPHONE ET LES TEXTES (dessinés avec Pillow)
=====================================================================
- HEURE : en haut à gauche, petite, comme la barre d'état d'un téléphone (JetBrains Mono 52 px blanc, ombre douce) : « 20:02 », « 21:00 »… Elle saute à chaque indication 🗂️ du script, avec un petit « tic ». Pas d'heure sur le plan 1, ni sur la liste des règles.
- SMS : les bulles apparaissent PAR-DESSUS le clip qui continue derrière (le clip est assombri à 60 % et légèrement flouté pendant que les SMS sont à l'écran). Style iMessage sombre : en haut le nom du contact « Mme Vasseur » (Inter SemiBold 40 px gris clair) ; bulles grises arrondies à gauche pour elle, bulles BLEUES #2F7BF6 à droite pour Inès ; texte Inter 46 px blanc ; heure du message en petit gris. Chaque bulle arrive avec un petit glissement vers le haut (0,15 s) + le son de SMS. Avant les réponses importantes, une bulle « … » (elle écrit) pendant 0,8 s.
- APPEL (plan 17) : écran d'appel sombre plein écran 1,5 s : rond avec l'initiale « V », « Mme Vasseur », « Appel… », un bouton rouge ; puis on revient sur le clip V14 en gardant le son de la sonnerie.
- LA LISTE DES RÈGLES (plan 3) : par-dessus V03 (qui continue derrière, assombri), une feuille blanche manuscrite propre, légèrement inclinée (-2°), police manuscrite libre (Google Fonts « Caveat » ou « Patrick Hand ») 58 px noire. Les 5 règles s'écrivent une à une, synchronisées avec la voix. Le n°5 est souligné trois fois en rouge (trois traits qui se dessinent avec un crissement de feutre). La liste doit tenir en 11 à 13 s maximum (lecture rapide des 1 à 4, lente pour la 5).
- TAMPONS « RÈGLE 2 ✓ », « RÈGLE 3 ✓ » : petits (largeur 360 px), en haut à droite sous l'heure, verts #3BB273, inclinés -8°, apparition en 0,12 s avec un petit choc sourd, visibles 1,2 s. Ils ne coupent PAS l'histoire.
- TEXTE D'ACCROCHE (plan 1) : « 🧵 5 RÈGLES. » puis « J'EN AI ENFREINT UNE. » au centre-haut, Montserrat Black 92 px blanc, « UNE » en rouge #E0242B, contour noir fin. Il apparaît dès la 1re image.
- QUESTION FINALE : « TU SERAIS MONTÉ(E) ? 👇 » Montserrat Black 84 px, « MONTÉ(E) » en rouge.

=====================================================================
5. SOUS-TITRES
=====================================================================
Mot à mot, groupes de 1 à 3 mots, synchronisés sur les minutages d'edge-tts (WordBoundary), jamais en retard.
Centrés à 66 % de la hauteur, Montserrat Black 80 px, MAJUSCULES, blanc, contour noir 5 px + ombre douce. Un mot-clé par phrase en ROUGE #E0242B (« grenier », « interphone », « soif », « sa chambre », « mon prénom », « je descends »…). Pop 85 → 100 % en 0,07 s.
Les répliques de Noé en jaune moutarde #F2B33D ; celles de Mme Vasseur en blanc italique ; celles de LA CHOSE en rouge italique qui tremble légèrement.
Pas de sous-titres pendant que les SMS sont à l'écran (on lit les bulles), sauf si la narratrice dit autre chose.

=====================================================================
6. VOIX (edge-tts ; une réplique = un fichier dans travail/voix/)
=====================================================================
- INÈS, la narratrice (19 ans, raconte au passé, voix jeune et naturelle, posée au début, de plus en plus tendue, chuchotée vers la fin) : fr-FR-VivienneMultilingualNeural (sinon fr-FR-DeniseNeural). Débit rate +6 %. Passages d'action : +12 %. Passages de peur (plans 15 à 22) : rate 0 %, volume un peu plus bas, plus proche du micro.
  Pour qu'elle paraisse humaine : génère chaque phrase séparément ; varie légèrement le pitch d'une phrase à l'autre (-2 à +2 Hz) ; garde les « … » ; ajoute 4-5 petites inspirations discrètes (-30 dB) avant les phrases fortes ; traitement : passe-haut 80 Hz, +2 dB à 3 kHz, compression douce, très légère réverbération de pièce. 0,2 s entre deux phrases, 0,8 s sur les ⏸.
- MME VASSEUR (polie, calme, un peu trop calme) : fr-FR-DeniseNeural, rate -5 %, pitch -2 Hz.
- NOÉ (7 ans) : fr-FR-EloiseNeural, rate -5 %, pitch -2 Hz. Plan 14 : sa phrase « Elle aussi, elle a soif » est DOUBLÉE par la voix de Mme Vasseur décalée de 40 ms, une octave plus bas, à 50 %.
- LA FAUSSE MME VASSEUR (interphone plan 9) : voix de Mme Vasseur + filtre passe-bande 300-3000 Hz + grésillement (bruit filtré) = son d'interphone.
- LA CHOSE (plans 18 et 21) : voix de Mme Vasseur rate -20 %, trop douce, puis une 2e copie un demi-ton plus bas décalée de 30 ms, réverbération de grenier (longue et sombre). Plan 21 « …je descends » : chuchoté très près, stéréo d'un seul côté.
- Ducking : ambiance et musique -9 dB pendant que quelqu'un parle.

=====================================================================
7. SONS ET MUSIQUE (l'atmosphère)
=====================================================================
Si sources/sons/ contient des fichiers, utilise-les. Je peux télécharger de vrais bruitages gratuits sur pixabay.com/fr/sound-effects (dis-moi lesquels te manquent) : frigo_bourdonnement, porte_entree, voiture_part, horloge, plancher_craque, sms, interphone_buzz, interphone_grésillement, pas_enfant, verre, trainee_plafond, sonnerie_telephone, sonnerie_etouffee, cheveux_frottement, grattements_porte, coeur, impact_grave, riser, drone, vent_nuit, porte_ouvre. Sinon FABRIQUE-LES (Python/ffmpeg) et dis-moi lesquels sont fabriqués.
- Fond permanent : « room tone » de maison la nuit (bruit brun très bas -36 dB) + le bourdonnement du frigo dans la cuisine (plans 1-3 et 23) + vent léger dehors.
- Musique : un DRONE sombre (sinusoïdes graves désaccordées + bruit filtré + une note aiguë lointaine) qui commence très bas au plan 4 et MONTE doucement jusqu'au plan 22 (-30 → -17 dB). Il se COUPE NET au plan 22 (choc), puis revient très bas et froid pour la fin.
- Sons précis : porte d'entrée + voiture qui s'éloigne (4) ; craquement au plafond (6) ; SMS (7, 10, 16, 25) ; BZZZT d'interphone fort et sec (8) ; grésillement (9, 11) ; pas pieds nus + verre (12) ; quelque chose qui RAMPE au-dessus du plafond, de gauche à droite (15) ; sonnerie d'appel dans le téléphone PUIS la même sonnerie, étouffée, au-dessus (17) — c'est le moment le plus fort, laisse la sonnerie du grenier seule 1 s ; cheveux qui frottent (18) ; cœur qui accélère (19-21) ; grattements sur le parquet (21) ; impact grave (22) ; porte d'entrée (22) ; billets (23).
- RISER (montée de 2 s) puis SILENCE TOTAL 0,5 s avant les chocs des plans 9, 17, 21 et 22.
- Mixage normalisé -14 LUFS, crête -1 dBTP. Les voix toujours compréhensibles.

=====================================================================
8. SCRIPT COMPLET AVEC MINUTAGE (≈ 2 min 05)
=====================================================================
Format : n° · temps visé · clip · heure à l'écran · voix / sons. ⏸ = 0,8 s de silence. Le minutage s'adapte à la durée réelle des voix.

1 · 0:00–0:05 · V01 · — · frigo · INÈS : « Il y a deux ans, j'ai fait du baby-sitting pour une famille… qui avait cinq règles. » · texte d'accroche dès la 1re image.
2 · 0:05–0:08 · V02 (0–2,3 s) · — · INÈS : « La mère m'a montré la liste sur le frigo. » / MME VASSEUR : « Suis-les. Toutes. »
3 · 0:08–0:20 · V03 (1,6–5 s, ralenti) + LA LISTE · — · INÈS lit vite : « Un. Noé doit être couché à 21 heures. Deux. Après 22 heures, ne réponds pas à l'interphone. Trois. Si Noé dit qu'il a soif après 23 heures, ne lui donne rien. Quatre. Si on t'écrit qu'on rentre plus tôt, appelle-nous avant d'ouvrir. » puis lentement : « Cinq. Ne monte jamais au grenier. » ⏸ « Même si on t'appelle. » · feutre qui crisse 3 fois
4 · 0:20–0:24 · V04 · 20:02 · porte + voiture · INÈS : « Ils sont partis à vingt heures. » / « Noé avait sept ans. »
5 · 0:24–0:29 · V05 · 21:00 · NOÉ : « Tu sais pourquoi on monte pas au grenier ? » ⏸ « Parce que c'est sa chambre. »
6 · 0:29–0:32 · V06 (0–3 s) · 21:04 · craquement au plafond · INÈS : « J'ai pas demandé à qui. »
7 · 0:32–0:37 · V07 (début) + SMS · 21:42 · Mme Vasseur : « Tout se passe bien ? 😊 » / Inès : « Oui ! Il dort 😊 » / Mme Vasseur : « Parfait. Tu as bien lu la règle 5 ? » · INÈS (voix basse) : « Elle m'a demandé ça deux fois dans la soirée. »
8 · 0:37–0:41 · V07 (fin, l'interphone s'allume) · 22:14 · BZZZT · INÈS : « À 22 h 14, l'interphone a sonné. »
9 · 0:41–0:46 · V08 · 22:14 · grésillement · LA FAUSSE MME VASSEUR (interphone) : « C'est moi. J'ai oublié mes clés. » ⏸ « Ouvre. » · petit zoom-coup sur « Ouvre ».
10 · 0:46–0:51 · V08 (ralenti) ou V07 + SMS · 22:15 · Inès : « Vous êtes devant la porte ?? » / « … » / Mme Vasseur : « Non. On est au restaurant. » / « N'ouvre pas. » · INÈS : « Règle numéro deux. » · tampon RÈGLE 2 ✓
11 · 0:51–0:56 · V09 · 22:16 · grésillement qui coupe · INÈS : « Sur l'écran, elle a reculé… » ⏸ « à quatre pattes. »
12 · 0:56–1:00 · V10 · 23:03 · pas pieds nus · NOÉ : « J'ai soif. » · INÈS : « À vingt-trois heures, Noé était debout dans le couloir. »
13 · 1:00–1:04 · V11 · 23:03 · INÈS : « Règle numéro trois. Je lui ai dit non. » / NOÉ : « S'il te plaît… »
14 · 1:04–1:08 · V12 (0–4 s) · 23:04 · NOÉ (voix doublée) : « Elle aussi, elle a soif. » · tampon RÈGLE 3 ✓
15 · 1:08–1:12 · V13 (0–4,5 s) · 23:05 · quelque chose rampe au plafond · INÈS : « Au-dessus de moi, quelque chose a rampé… jusqu'à la trappe. »
16 · 1:12–1:17 · V14 (début) + SMS · 23:47 · Mme Vasseur : « On rentre plus tôt. Ouvre-nous 😊 » · INÈS : « Règle numéro quatre. » / « Je l'ai appelée. »
17 · 1:17–1:22 · écran d'APPEL 1,5 s puis V14 · 23:47 · sonnerie → riser → silence → la sonnerie ÉTOUFFÉE au-dessus · INÈS : « Son téléphone a sonné. » ⏸ « Dans le grenier. » · choc
18 · 1:22–1:26 · V15 (0–2,5 s, ralenti) · 23:48 · cheveux qui frottent · LA CHOSE : « Inès ? Monte. C'est moi. »
19 · 1:26–1:30 · V16 · 23:48 · cœur · INÈS : « Elle connaissait mon prénom. » / « Je ne l'avais jamais dit à personne ici. »
20 · 1:30–1:35 · V17 · 00:05 · cœur · INÈS (chuchoté) : « J'ai pris Noé. On s'est enfermés dans sa chambre. » / « Elle m'a appelée pendant une heure. »
21 · 1:35–1:40 · V18 · 01:07 · silence… grattements · LA CHOSE (chuchoté, tout près) : « Si tu ne montes pas… » ⏸ « …je descends. »
22 · 1:40–1:45 · V19 · 01:07 · riser → silence → IMPACT, la musique coupe net · aucune voix pendant 2 s (on regarde la créature), puis INÈS (sur la fin du plan) : « À 1 h 12, la porte d'entrée s'est ouverte. » · porte d'entrée
23 · 1:45–1:51 · V20 · 01:15 · frigo, billets · MME VASSEUR : « Tu as respecté les cinq règles ? » / INÈS : « Oui. » / MME VASSEUR : « Bien. » ⏸ « La dernière n'avait pas fait attention à la quatre. »
24 · 1:51–1:55 · V21 (0–4 s) · 01:20 · vent · INÈS : « Je ne suis jamais revenue. »
25 · 1:55–2:05 · V21 (ralenti, assombri) + SMS final plein centre · « Hier » · SMS de Mme Vasseur, hier 03:12 : « Les enfants te réclament samedi. » / « Surtout celle du grenier. » puis la bulle « … » qui RESTE · INÈS : « Ça… je l'ai reçu hier. » · question finale « TU SERAIS MONTÉ(E) ? 👇 » · noir 0,5 s · la vidéo se termine sur le son de la bulle « … ».

=====================================================================
9. VÉRIFICATION AVANT DE ME DIRE QUE C'EST FINI
=====================================================================
1. Planche de contrôle : une image toutes les 2 s en mosaïque (sortie/controle_v1.jpg). Regarde-la toi-même : pas de bande noire, pas de texte coupé ou hors zones sûres, AUCUNE des parties de clips interdites (section 3) n'est utilisée, les SMS sont lisibles.
2. Voix / sous-titres synchronisés (3 extraits de 3 s).
3. Son : -14 LUFS ±1, crête ≤ -1 dBTP, voix toujours compréhensibles.
4. Durée 1 min 55 à 2 min 15, 1080x1920, 30 i/s.
5. Le récit ne s'arrête jamais plus de 1,5 s sans voix, SAUF les silences voulus (⏸, plans 17 et 22).
6. Résumé simple : ce qui est fait, les sons fabriqués ou téléchargés, ce que je dois regarder en premier. Ne publie rien.
```

---

## 💡 Après le premier rendu
Regarde-le **sur ton téléphone, le son allumé**, puis donne tes corrections en une phrase. Claude les note dans `SUIVI.md`.
