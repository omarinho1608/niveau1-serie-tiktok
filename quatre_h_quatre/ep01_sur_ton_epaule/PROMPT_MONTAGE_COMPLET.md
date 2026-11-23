# 🎬 PROMPT DE MONTAGE COMPLET – 04:04, épisode 01 « Sur ton épaule » (partie 1)

⬅️ [Retour au script](script.md) · 🎞️ [Clips générés](rendus/)

> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code**. Il récupère lui-même les 11 clips sur GitHub.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel.
Règles : travaille toujours sur une copie (les originaux restent intacts), vérifie toi-même le résultat avant de me dire que c'est fini, ne publie jamais rien sans moi.

OBJECTIF : une vidéo TikTok d'horreur « POV + SMS » de 65 à 75 secondes, en français, pour les 16-25 ans, au style des comptes anglophones d'histoires « 3 AM » en dessin animé : dessin animé nocturne bleu, gros écrans de téléphone avec SMS, HUD avec l'heure, sous-titres mot à mot, fin sur un VOTE et « PARTIE 2 DEMAIN ».
Priorités : 1) le spectateur reste jusqu'au bout (accroche immédiate, une info ou une peur nouvelle toutes les 2-3 s) ; 2) l'histoire coule sans pause ; 3) une ambiance qui fait vraiment peur.

=====================================================================
0. FICHIERS
=====================================================================
git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok
Dossier de travail montage_0404_ep01/ (EN DEHORS du dépôt) : sources/ (copie), travail/, sortie/.
Copie dans sources/ : quatre_h_quatre/ep01_sur_ton_epaule/rendus/clips/V01.mp4 … V11.mp4 (720p, 9:16, 5 s, sans son).
Lis : quatre_h_quatre/README.md (le style de la série), ep01_sur_ton_epaule/script.md et rendus/README.md.
S'il existe SUIVI.md, applique-le ; sinon crée-le. Chaque correction que je te donne = une règle datée dans SUIVI.md.
Garde tes générateurs (HUD, téléphone, écran de vote) dans des scripts réutilisables (travail/outils/) : ils serviront à chaque épisode.

=====================================================================
1. OUTILS (gratuits)
=====================================================================
ffmpeg ; Python 3 + edge-tts, Pillow, numpy, scipy. Polices Google Fonts : « Montserrat » (Black Italic, ExtraBold), « Inter » (téléphone), « JetBrains Mono » (heure). Proxy pour edge-tts si besoin : --proxy "$HTTPS_PROXY".

=====================================================================
2. EXPORT
=====================================================================
1080x1920, 30 i/s, H.264 CRF 17 preset slow yuv420p + AAC 48 kHz 192 kb/s → sortie/0404_ep01_partie1_v1.mp4 (puis v2, v3… sans écraser).
Couverture : sortie/couverture.png = image de V08 (le reflet avec le grand sourire) + titre « SUR TON ÉPAULE » en Montserrat Black Italic blanc, « ÉPAULE » en rouge, petit badge « 04:04 · HISTOIRE #001 ».

=====================================================================
3. STYLE VISUEL
=====================================================================
- Clips agrandis pour remplir 1080x1920 (scale + crop centre, lanczos), jamais de bandes noires. V08 : recadre pour faire disparaître les petites icônes de téléphone en haut à droite (zoom 108 % minimum).
- Remonte légèrement les noirs (+6 %) sans changer les couleurs.
- Zoom avant lent sur chaque plan (100 → 104 %), 100 → 110 % sur les plans de tension (V04, V05, V08, V09, V11).
- Couches : grain fin (5 %), vignettage, très légère aberration chromatique.
- Coupes sèches. Chocs (plans 10 et 16) : zoom-coup 100 → 112 % en 0,1 s + tremblement 0,3 s + flash 2 images.
- Zones sûres TikTok : rien d'important dans les 320 px du bas, les 140 px de droite, les 150 px du haut (le HUD commence à 160 px du haut).

COUPES DES CLIPS (vérifiés image par image) :
| V05 | 0 à 2,5 s (ralenti 0,8x) | ensuite la main glisse et la manche sort du cadre |
| V10 | 0 à 2,5 s seulement (ralenti 0,8x) | ensuite Jade rentre et la porte se ferme |
| V11 | 2 à 5 s | le début est trop « mignon », la fin (yeux fixes, tête penchée) est la bonne |
| V08 | toute la durée, mais recadré | petites icônes de téléphone en haut à droite |
| autres | 0 à 5 s, coupe librement | OK |
Si un plan doit durer plus que la partie utilisable : ralenti max 0,8x (minterpolate blend), jamais d'image figée.

=====================================================================
4. ÉLÉMENTS GRAPHIQUES (Pillow)
=====================================================================
- BADGE D'OUVERTURE (0 à 2,5 s, centre-haut à 300 px) : petit rectangle noir arrondi, texte rouge « 04:04 · HISTOIRE #001 » (Montserrat ExtraBold 34 px), et dessous un encadré noir avec « SUR TON ÉPAULE » en blanc (Montserrat Black Italic 64 px).
- HUD (toute la vidéo après le badge, sauf l'écran de vote) en haut à gauche (x 60, y 170) : rectangle noir 70 % arrondi ; un point ROUGE qui clignote (1 Hz) ; l'heure « 04:04 » en JetBrains Mono Bold 76 px blanc avec « AM » minuscule à côté ; dessous en petit (Inter SemiBold 26 px, gris clair, majuscules espacées) « PARTIE 1 · TON SALON » ou « PARTIE 1 · L'ESCALIER ». L'heure passe à 04:05 au plan 8, 04:06 au plan 13, 04:07 au plan 16, avec un petit glitch.
- TÉLÉPHONE (plans 2, 5, 8, 12, 16) : un GRAND iPhone noir au centre (largeur 620 px), coins arrondis, encoche, barre d'état « 4:04 », en haut le contact (rond gris avec « J » + « Jade 🌙 »), bulles iMessage : grises à gauche pour Jade, BLEUES #2F7BF6 à droite pour toi, Inter 40 px blanc ; champ « Message » en bas. Le téléphone est tenu par une main simple (couleur peau claire, manche jaune moutarde) qui monte du bas de l'écran. Derrière, le clip précédent continue, assombri à 45 % et flouté. Chaque bulle arrive avec un petit glissement + son de SMS ; « … » (en train d'écrire) 0,7 s avant les réponses importantes.
  Le VOCAL (plan 2) : une bulle grise avec ▶ et une onde sonore verte qui s'anime pendant la lecture, durée « 0:04 ».
- SOUS-TITRES : 1 à 3 mots, MAJUSCULES, Montserrat Black Italic 82 px, blanc, contour noir 5 px + ombre, centrés à 64 % de la hauteur. Un mot-clé par phrase en JAUNE #FFC83D (ou ROUGE #E0242B pour les mots de danger : « PAS MOI », « CHOUCHOU », « SOURIRE », « MAIN »…). Pop 85 → 100 % en 0,07 s. Les répliques chuchotées de JADE en petit encadré noir avec guillemets en haut de l'écran (« — JADE · VOCAL — » puis la phrase en Montserrat Black Italic 44 px).
- ÉCRAN DE VOTE (fin, 6 à 8 s) : fond noir. En haut « UNE SEULE EST LA VRAIE. » (blanc, Montserrat Black 64 px) et « TU CROIS QUI ? » (rouge #E0242B). Deux cartes arrondies côte à côte (bord blanc fin) : à gauche une image de V07 (Jade du canapé) avec un bouton BLEU « LE CANAPÉ », à droite une image de V11 (Jade de l'escalier) avec un bouton ROUGE « L'ESCALIER ». Dessous « PARTIE 2 DEMAIN » (rouge, 54 px) et un bouton blanc arrondi « ABONNE-TOI ». Les cartes arrivent l'une après l'autre (0,2 s), légère pulsation des boutons.

=====================================================================
5. VOIX (edge-tts)
=====================================================================
- NARRATEUR (au « tu », présent, phrases très courtes, ton tendu et naturel, un peu chuchoté par moments) : fr-FR-RemyMultilingualNeural, rate +8 %, chaque phrase générée séparément, pitch varié de -2 à +2 Hz, 0,2 s entre les phrases, 0,7 s sur ⏸. Traitement : passe-haut 80 Hz, compression douce, +2 dB à 3 kHz, très légère réverbération.
- JADE (10 ans) : fr-FR-EloiseNeural, rate -5 %. Le VOCAL du plan 3 : chuchoté (volume bas, filtre « téléphone » 300-3400 Hz, souffle léger).
- LA JADE DU CANAPÉ : fr-FR-EloiseNeural rate -12 %, pitch -3 Hz, très proche du micro, un tout petit écho ; au plan 11, une 2e copie très grave (-7 demi-tons) mixée à 15 % pour qu'on sente que quelque chose cloche.
- JADE D'EN HAUT (plan 15) : Eloise rate -8 %, réverbération de cage d'escalier.
- PLAN 16 : les deux voix disent « C'est moi, la vraie » EN MÊME TEMPS (une à gauche, une à droite en stéréo).
- Ducking ambiance/musique -9 dB pendant les voix.

=====================================================================
6. SONS ET MUSIQUE
=====================================================================
Si sources/sons/ contient des fichiers (pixabay.com/fr/sound-effects), utilise-les, sinon fabrique-les et dis-moi lesquels.
- Fond : bourdonnement léger de télé + souffle de maison la nuit (-34 dB), en continu.
- Musique : drone sombre bas qui monte doucement du début au plan 15 (-30 → -18 dB), avec une petite note de boîte à musique désaccordée, très lointaine, à partir du plan 9. Coupure nette au plan 16.
- Vibration de téléphone (2), SMS (5, 8, 12), « tic » quand l'heure change, craquement de marche (6), respiration lente qui S'ARRÊTE (4 → 7), choc grave (10), frottement de tissu (13), grincement de porte (14), riser 2 s + silence 0,5 s avant les plans 10 et 16, tic-tac d'horloge sur l'écran de vote.
- Mixage -14 LUFS, crête -1 dBTP.

=====================================================================
7. SCRIPT (≈ 70 s) — n° · temps · clip · voix / texte
=====================================================================
1 · 0–4 s · V01 · badge + NARRATEUR : « Imagine, à 4 h 04, ta petite sœur dort sur ton épaule… et elle t'envoie un vocal depuis sa chambre. »
2 · 4–7 s · TÉLÉPHONE sur V01 assombri · vocal de « Jade 🌙 » qui arrive (0:04) · NARRATEUR : « Tu mets ton écouteur. »
3 · 7–11 s · V02 · JADE (vocal, chuchoté) : « Bouge pas. Celle sur toi… c'est pas moi. »
4 · 11–16 s · V03 · NARRATEUR : « Vous vous êtes endormies devant le film. » / « Tu sens son poids. Sa respiration. » ⏸ « Enfin… tu crois. »
5 · 16–20 s · TÉLÉPHONE sur V03 · toi : « T'es sur moi là ?? » · Jade : « Non. Je suis montée me coucher à minuit. » / « Je t'ai même dit bonne nuit. »
6 · 20–24 s · V04 · HUD « L'ESCALIER » · NARRATEUR : « Sa porte est ouverte. » / « Il y a de la lumière. »
7 · 24–28 s · V05 · HUD « TON SALON » · NARRATEUR : « Ton regard descend sur son poignet. » / « Pas de chouchou rouge. » ⏸ « Jade ne l'enlève jamais. »
8 · 28–33 s · TÉLÉPHONE sur V05 · 04:05 · toi : « Prouve-le. C'est quoi mon surnom ? » · « … » · Jade : « Patate. Personne d'autre le sait. » · NARRATEUR : « C'est vrai. Personne. »
9 · 33–37 s · V06 · LA JADE DU CANAPÉ (chuchoté, les yeux fermés) : « Patate… pourquoi tu lui réponds ? »
10 · 37–40 s · V07 · riser → silence → CHOC · NARRATEUR : « Elle a lu par-dessus ton épaule. »
11 · 40–45 s · V08 · ELLE (trop douce) : « C'est moi, Jade. Celle d'en haut t'a pris ton téléphone… pour t'écrire. » · NARRATEUR (bas) : « Dans le reflet de la télé… » ⏸
12 · 45–49 s · TÉLÉPHONE sur V08 · Jade : « Ne la laisse pas te tenir la main. » / « Si elle te tient la main, elle prend ta place. »
13 · 49–53 s · V09 · 04:06 · NARRATEUR : « Sous le plaid… quelque chose cherche tes doigts. »
14 · 53–56 s · V10 (0–2,5 s, ralenti) · HUD « L'ESCALIER » · grincement · NARRATEUR : « Là-haut, la porte s'ouvre. »
15 · 56–61 s · V11 · JADE D'EN HAUT : « Viens. Vite. Avant qu'elle se réveille vraiment. »
16 · 61–64 s · TÉLÉPHONE + V07 en fond · 04:07 · nouveau vocal qui arrive + les deux voix en même temps : « C'est moi, la vraie. » · CHOC
17 · 64–72 s · ÉCRAN DE VOTE · NARRATEUR : « Une seule est ta sœur. » ⏸ « Tu choisis qui ? »

=====================================================================
8. VÉRIFICATION
=====================================================================
1. Planche de contrôle (une image toutes les 2 s) → sortie/controle_v1.jpg. Regarde-la : pas de bande noire, aucun texte coupé ni hors zones sûres, icônes de V08 invisibles, V05 et V10 jamais au-delà de 2,5 s, V11 seulement de 2 à 5 s, SMS lisibles.
2. Voix/sous-titres synchronisés (3 extraits). 3. -14 LUFS ±1, crête ≤ -1 dBTP. 4. 65-75 s, 1080x1920, 30 i/s.
5. Résumé simple de ce qui est fait et des sons fabriqués. Ne publie rien.
```
