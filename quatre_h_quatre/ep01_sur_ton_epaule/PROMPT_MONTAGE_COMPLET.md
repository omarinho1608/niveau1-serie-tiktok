# 🎬 PROMPT DE MONTAGE COMPLET – 04:04, épisode 01 « Sur ton épaule » (histoire complète)

⬅️ [Retour au script](script.md) · 🎞️ [Clips générés](rendus/)

> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code**. Il récupère lui-même les 20 clips (nouveau style) sur GitHub.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel.
Règles : travaille toujours sur une copie (les originaux restent intacts), vérifie toi-même le résultat avant de me dire que c'est fini, ne publie jamais rien sans moi.

OBJECTIF : UNE SEULE vidéo TikTok d'horreur « POV + SMS » de 1 min 45 à 2 min, avec l'histoire COMPLÈTE (début, milieu, fin, pas de partie 2), en français, pour les 16-25 ans, au style des comptes anglophones d'histoires « 3 AM » en dessin animé : dessin animé nocturne bleu, gros écrans de téléphone avec SMS, HUD avec l'heure, sous-titres mot à mot, et une chute finale qui glace + une question au spectateur.
Priorités : 1) le spectateur reste jusqu'au bout (accroche immédiate, une info ou une peur nouvelle toutes les 2-3 s) ; 2) l'histoire coule sans pause ; 3) une ambiance qui fait vraiment peur.

=====================================================================
0. FICHIERS
=====================================================================
git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok
Dossier de travail montage_0404_ep01/ (EN DEHORS du dépôt) : sources/ (copie), travail/, sortie/.
Copie dans sources/ : quatre_h_quatre/ep01_sur_ton_epaule/rendus/clips/V01.mp4 … V21.mp4 (il n'y a PAS de V18, c'est normal) (720p, 9:16, 5 s, sans son). STYLE : dessin plat minimaliste, têtes rondes blanches, tout baigné dans un bleu indigo froid et brumeux ; la créature (poupée au visage de porcelaine fissuré, sourire cousu) est beaucoup plus détaillée que les autres personnages.
Lis : quatre_h_quatre/README.md (le style de la série), ep01_sur_ton_epaule/script.md et rendus/README.md.
S'il existe SUIVI.md, applique-le ; sinon crée-le. Chaque correction que je te donne = une règle datée dans SUIVI.md.
Garde tes générateurs (HUD, téléphone, question finale) dans des scripts réutilisables (travail/outils/) : ils serviront à chaque épisode.

=====================================================================
1. OUTILS (gratuits)
=====================================================================
ffmpeg ; Python 3 + edge-tts, Pillow, numpy, scipy. Polices Google Fonts : « Montserrat » (Black Italic, ExtraBold), « Inter » (téléphone), « JetBrains Mono » (heure). Proxy pour edge-tts si besoin : --proxy "$HTTPS_PROXY".

=====================================================================
2. EXPORT
=====================================================================
1080x1920, 30 i/s, H.264 CRF 17 preset slow yuv420p + AAC 48 kHz 192 kb/s → sortie/0404_ep01_v1.mp4 (puis v2, v3… sans écraser).
Couverture : sortie/couverture.png = image de V15 (la poupée qui t'attrape le visage) + titre « SUR TON ÉPAULE » en Montserrat Black Italic blanc, « ÉPAULE » en rouge, petit badge « 04:04 · HISTOIRE #001 ».

=====================================================================
3. STYLE VISUEL
=====================================================================
- Clips agrandis pour remplir 1080x1920 (scale + crop centre, lanczos), jamais de bandes noires.
- Ne change PAS les couleurs (le bleu indigo brumeux est la DA). Pas d'éclaircissement.
- Zoom avant lent sur chaque plan (100 → 104 %), 100 → 110 % sur les plans de tension (V04, V05, V09, V10, V12, V13, V15, V16, V19, V21).
- Couches : grain fin (5 %), vignettage, très légère aberration chromatique.
- Coupes sèches. Chocs (plans 11 et 17) : zoom-coup 100 → 112 % en 0,1 s + tremblement 0,3 s + flash 2 images.
- Zones sûres TikTok : rien d'important dans les 320 px du bas, les 140 px de droite, les 150 px du haut (le HUD commence à 160 px du haut).

COUPES DES CLIPS (vérifiés image par image) : tous les clips sont utilisables sur toute leur durée, sauf :
| V08 | flash de 0,6 s seulement (voir plan 11) |
| V15 | recadre légèrement (zoom 106 %) pour cacher de petites icônes en haut à droite |
| V16 | garde TOUT le clip : à la fin, le visage de la poupée surgit en gros plan = jump scare (mets le choc pile dessus) |
| V21 | 0 à 4 s seulement (la fin devient bizarre) |
Si un plan doit durer plus que la partie utilisable : ralenti max 0,8x (minterpolate blend), jamais d'image figée.

=====================================================================
4. ÉLÉMENTS GRAPHIQUES (Pillow)
=====================================================================
- BADGE D'OUVERTURE (0 à 2,5 s, centre-haut à 300 px) : petit rectangle noir arrondi, texte rouge « 04:04 · HISTOIRE #001 » (Montserrat ExtraBold 34 px), et dessous un encadré noir avec « SUR TON ÉPAULE » en blanc (Montserrat Black Italic 64 px).
- HUD (toute la vidéo après le badge, sauf la question finale) en haut à gauche (x 60, y 170) : rectangle noir 70 % arrondi ; un point ROUGE qui clignote (1 Hz) ; l'heure « 04:04 » en JetBrains Mono Bold 76 px blanc avec « AM » minuscule à côté ; dessous en petit (Inter SemiBold 26 px, gris clair, majuscules espacées) « TON SALON », « L'ESCALIER » ou « DEHORS ». L'heure passe à 04:05 au plan 9, 04:06 au plan 14, 04:07 au plan 17, 04:08 au plan 21, 04:09 au plan 23, avec un petit glitch.
- TÉLÉPHONE (plans 2, 5, 9, 13, 18) : un GRAND iPhone noir au centre (largeur 620 px), coins arrondis, encoche, barre d'état « 4:04 », en haut le contact (rond gris avec « J » + « Jade 🌙 »), bulles iMessage : grises à gauche pour Jade, BLEUES #2F7BF6 à droite pour toi, Inter 40 px blanc ; champ « Message » en bas. Le téléphone est tenu par une main simple (couleur peau claire, manche jaune moutarde) qui monte du bas de l'écran. Derrière, le clip précédent continue, assombri à 45 % et flouté. Chaque bulle arrive avec un petit glissement + son de SMS ; « … » (en train d'écrire) 0,7 s avant les réponses importantes.
  Le VOCAL (plan 2) : une bulle grise avec ▶ et une onde sonore verte qui s'anime pendant la lecture, durée « 0:04 ».
- SOUS-TITRES : 1 à 3 mots, MAJUSCULES, Montserrat Black Italic 82 px, blanc, contour noir 5 px + ombre, centrés à 64 % de la hauteur. Un mot-clé par phrase en JAUNE #FFC83D (ou ROUGE #E0242B pour les mots de danger : « PAS MOI », « CHOUCHOU », « SOURIRE », « MAIN »…). Pop 85 → 100 % en 0,07 s. Les répliques chuchotées de JADE en petit encadré noir avec guillemets en haut de l'écran (« — JADE · VOCAL — » puis la phrase en Montserrat Black Italic 44 px).
- QUESTION FINALE (plan 26, sur V21 assombri puis noir) : « ET TOI… TU L'AURAIS RECONNUE ? 👇 » en Montserrat Black Italic 80 px blanc, « RECONNUE » en rouge, + petit bouton blanc arrondi « ABONNE-TOI POUR L'HISTOIRE #002 ».

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
- Musique : drone sombre bas qui monte doucement du début au plan 20 (-30 → -16 dB), avec une petite note de boîte à musique désaccordée à partir du plan 10. Pendant la fuite (plans 21-22) : pulsation rapide de basse + respiration haletante. Plan 23-24 (dehors, câlin) : calme trompeur, juste le vent et la neige. Plan 25 : la boîte à musique revient, seule, désaccordée. Coupure nette sur le dernier mot.
- Vibration de téléphone (2, 18), SMS (5, 9, 13, 18), « tic » quand l'heure change, craquement de marche (6), respiration lente qui S'ARRÊTE (4 → 7), choc grave (10), frottement de tissu (13), grincement de porte (14), riser 2 s + silence 0,5 s avant les plans 11, 17, 19 et 25, porte d'entrée qui claque (22), vent et pas dans la neige (23-24).
- Mixage -14 LUFS, crête -1 dBTP.

=====================================================================
7. SCRIPT (≈ 75 s) — n° · temps · clip · voix / texte
=====================================================================
1 · 0–4 s · V01 · badge + NARRATEUR : « Imagine, à 4 h 04, ta petite sœur dort sur ton épaule… et elle t'envoie un vocal depuis sa chambre. »
2 · 4–7 s · TÉLÉPHONE sur V01 assombri · vocal de « Jade 🌙 » qui arrive (0:04) · NARRATEUR : « Tu mets ton écouteur. »
3 · 7–11 s · V02 (ton visage inquiet) · JADE (vocal, chuchoté) : « Bouge pas. Celle sur toi… c'est pas moi. »
4 · 11–16 s · V03 · NARRATEUR : « Vous vous êtes endormies devant le film. » / « Tu sens son poids. » ⏸ « Mais tu ne l'entends plus respirer. »
5 · 16–20 s · TÉLÉPHONE sur V03 · toi : « T'es sur moi là ?? » · Jade : « Non. Je suis montée me coucher à minuit. » / « Je t'ai même dit bonne nuit. »
6 · 20–24 s · V04 · HUD « L'ESCALIER » · NARRATEUR : « Sa porte est ouverte. » / « Il y a de la lumière. »
7 · 24–27 s · V05 · HUD « TON SALON » · NARRATEUR : « Ton regard descend sur son poignet. » / « Pas de chouchou rouge. »
8 · 27–31 s · V07 (tu pleures en silence) · NARRATEUR : « Jade ne l'enlève jamais. » ⏸ « Même pour dormir. »
9 · 31–36 s · TÉLÉPHONE sur V07 · 04:05 · toi : « Prouve-le. C'est quoi mon surnom ? » · « … » · Jade : « Patate. Personne d'autre le sait. »
10 · 36–40 s · V06 · LA JADE DU CANAPÉ (chuchoté, les yeux fermés) : « Patate… pourquoi tu lui réponds ? »
11 · 40–43 s · riser → silence → FLASH V08 (0,6 s, le visage de poupée fissuré, avec choc + glitch) → retour sur V03 (Jade normale, comme si de rien n'était) · NARRATEUR (bas) : « Une demi-seconde… son visage n'était plus le sien. »
12 · 43–48 s · V09 · NARRATEUR : « Dans le reflet noir de la télé… il n'y a pas Jade. » ⏸ « Il y a ÇA. »
13 · 48–52 s · TÉLÉPHONE sur V09 assombri · Jade : « Ne la laisse pas te tenir la main. » / « Si elle te tient la main, elle prend ta place. »
14 · 52–56 s · V10 · 04:06 · NARRATEUR : « Sous le plaid… quelque chose cherche tes doigts. »
15 · 56–60 s · V11 · HUD « L'ESCALIER » · grincement · NARRATEUR : « Là-haut, quelqu'un te fait signe de monter. »
16 · 60–64 s · V12 · JADE D'EN HAUT (douce) : « Viens. Vite. Avant qu'elle se réveille vraiment. » · NARRATEUR : « …sa tête penche beaucoup trop. »
17 · 64–68 s · V13 · 04:07 · riser → silence → CHOC · les deux voix en même temps : « C'est moi, la vraie. »
18 · 68–72 s · TÉLÉPHONE sur V13 assombri · vibration · Jade : « Je suis pas dans ma chambre. » / « … » / « Regarde sous le canapé. »
19 · 72–76 s · V14 · NARRATEUR (chuchoté) : « Sous le canapé… » ⏸ « Jade. La vraie. Avec son chouchou. » · Jade, un doigt sur la bouche : « Chut… »
20 · 76–80 s · V15 · riser → silence → CHOC · NARRATEUR : « Celle sur ton épaule a vu ce que tu regardais. » · LA CHOSE (voix trop grave, tout près) : « Patate… »
21 · 80–85 s · V16 · HUD « L'ESCALIER » · bruit de mains qui claquent sur les marches, de plus en plus vite · NARRATEUR (rapide) : « En haut, l'autre descend. » / « À quatre pattes. » · JUMP SCARE sur le gros plan final du clip.
22 · 85–89 s · V17 · HUD « TON SALON » · NARRATEUR (rapide, essoufflé) : « Tu la tires de là. » / « Tu cours. » / « Tu ne te retournes pas. »
23 · 89–93 s · V19 · HUD « DEHORS » · 04:09 · vent, neige · NARRATEUR : « Dehors, tu te retournes quand même. » ⏸ « Elles sont deux. À la fenêtre. »
24 · 93–98 s · V20 · NARRATEUR (la voix tremble, soulagée) : « Tu la serres fort. » / « Elle est là. Elle est vraie. » / « Elle a son chouchou. »
25 · 98–102 s · V21 (0–4 s) · boîte à musique seule · JADE (tout près de ton oreille, douce… puis la voix se double d'une voix grave) : « Merci de m'avoir choisie… » ⏸ « …Patate. »
26 · 102–107 s · V21 assombri puis noir · QUESTION FINALE · NARRATEUR : « Personne d'autre ne connaissait ce surnom. » ⏸ « Sauf celles qui t'écoutent. »

=====================================================================
8. VÉRIFICATION
=====================================================================
1. Planche de contrôle (une image toutes les 2 s) → sortie/controle_v1.jpg. Regarde-la : pas de bande noire, aucun texte coupé ni hors zones sûres, le flash V08 dure bien 0,6 s, SMS lisibles.
2. Voix/sous-titres synchronisés (3 extraits). 3. -14 LUFS ±1, crête ≤ -1 dBTP. 4. 1 min 40 à 2 min, 1080x1920, 30 i/s.
5. Résumé simple de ce qui est fait et des sons fabriqués. Ne publie rien.
```
