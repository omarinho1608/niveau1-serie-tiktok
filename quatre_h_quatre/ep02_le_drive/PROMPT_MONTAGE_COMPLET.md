# 🎬 PROMPT DE MONTAGE COMPLET – 04:04, épisode 02 « Le drive de 4 h 04 » (histoire complète)

⬅️ [Script](script.md) · 🎞️ [Clips](rendus/)

> Colle le bloc ci-dessous dans **n'importe quelle session Claude Code**. Il récupère lui-même les 14 clips sur GitHub.
> Il réutilise les mêmes outils que l'épisode 01 (HUD, téléphone, sous-titres) : s'ils existent déjà dans ton dossier de montage, réutilise-les.

---

```text
Tu es mon monteur vidéo. Je ne sais pas coder : fais tout toi-même, explique-moi simplement ce que tu fais, et demande-moi avant d'installer un logiciel.
Règles : travaille toujours sur une copie (les originaux restent intacts), vérifie toi-même le résultat avant de me dire que c'est fini, ne publie jamais rien sans moi.

OBJECTIF : UNE vidéo TikTok d'horreur complète de 1 min 35 à 1 min 50, en français, pour les 16-25 ans. Style « histoire POV au tu » en dessin animé façon 3D (contours noirs épais, grosses têtes rondes, grands yeux, nuit, néons rouges), avec HUD, écran de téléphone, sous-titres mot à mot et une chute finale qui retourne tout.
Priorités : 1) accroche immédiate et une info/peur nouvelle toutes les 2-3 s ; 2) l'histoire coule sans pause ; 3) une ambiance qui fait vraiment peur.

=====================================================================
0. FICHIERS
=====================================================================
git clone --depth 1 -b claude/pensive-ramanujan-14exqk https://github.com/omarinho1608/niveau1-serie-tiktok (ou git pull si déjà cloné)
Dossier de travail montage_0404_ep02/ (EN DEHORS du dépôt) : sources/, travail/, sortie/.
Copie dans sources/ : quatre_h_quatre/ep02_le_drive/rendus/clips/V01 … V15.mp4 (il n'y a PAS de V08 : le plan 8 est un écran de téléphone). 720p, 9:16, 5 s, sans son.
Lis quatre_h_quatre/ep02_le_drive/script.md. S'il existe SUIVI.md (mes règles de montage), applique-le.

=====================================================================
1. OUTILS ET EXPORT
=====================================================================
ffmpeg ; Python 3 + edge-tts, Pillow, numpy, scipy ; polices Montserrat (Black Italic, ExtraBold), Inter, JetBrains Mono.
Export 1080x1920, 30 i/s, H.264 CRF 17 + AAC 192 kb/s → sortie/0404_ep02_v1.mp4. Couverture : image de V10 (ton double et l'employé qui sourient) + « LE DRIVE DE 4 H 04 » en Montserrat Black Italic, « 4 H 04 » en rouge.

=====================================================================
2. STYLE VISUEL ET COUPES
=====================================================================
- Clips agrandis pour remplir 1080x1920 (scale + crop centre). Ne change pas les couleurs.
- V02 : le personnage est petit au centre d'un cadre noir → zoom 160 % centré sur Sarah et la borne.
- Zoom lent sur chaque plan (100 → 104 %), 100 → 110 % sur V06, V07, V10, V11, V14, V15.
- Couches : grain fin 5 %, vignettage, légère aberration chromatique.
- Coupes sèches ; chocs (plans 11 et 15) : zoom-coup 100 → 112 % en 0,1 s + tremblement 0,3 s + flash 2 images.
- Zones sûres TikTok : rien d'important dans les 320 px du bas, 140 px de droite, 150 px du haut.
COUPES (vérifiées image par image) :
| V12 | 0 à 2 s seulement (ralenti 0,8x) | ensuite la voiture réapparaît |
| V15 | 0 à 4 s | des mains entrent par le bas à la fin |
| autres | 0 à 5 s | OK |

=====================================================================
3. ÉLÉMENTS GRAPHIQUES (Pillow)
=====================================================================
- BADGE d'ouverture (0-2,5 s) : « 04:04 · HISTOIRE #002 » en rouge + encadré « LE DRIVE DE 4 H 04 ».
- HUD en haut à gauche (même style que l'épisode 01) : point rouge qui clignote, heure « 04:04 » puis 04:05 (plan 6), 04:06 (plan 10), 04:30 (plan 14) ; dessous « LE DRIVE » puis « LA ROUTE » (plan 13) puis « CHEZ TOI » (plan 14).
- TICKET (plans 5 et 16) : par-dessus V05, dessine en police monospace noire sur le papier du ticket, ligne par ligne comme une imprimante (petit bruit d'imprimante thermique) :
  « LE GRAND MIAM — 24H/24 » / « COMMANDE N°4 » / « CLIENTE : SARAH » / « 23 RUE DES LILAS » / « 1 PERSONNE » / « HEURE : 04:04 ».
  Plan 16 : la même chose + une dernière ligne qui s'imprime en ROUGE : « COMMANDE LIVRÉE ✓ ».
- TÉLÉPHONE (plan 8) : grand iPhone noir au centre, tenu par une main à manche jaune moutarde, contact « Maman ❤️ », bulles grises : « T'es où ? » / « Tu viens de rentrer non ? » / « Je t'entends dans ta chambre. » (une par une, son de SMS), sur V07 assombri et flouté derrière.
- SOUS-TITRES : 1 à 3 mots, MAJUSCULES, Montserrat Black Italic 82 px, blanc + contour noir, centrés à 64 % ; un mot-clé en jaune #FFC83D ou rouge #E0242B. Répliques de l'EMPLOYÉ/INTERPHONE en encadré noir en haut (« — L'EMPLOYÉ — » + phrase).
- QUESTION FINALE (plan 16) : « ET TOI… TU SERAIS REPARTIE ? 👇 » en Montserrat Black Italic 80 px, « REPARTIE » en rouge.

=====================================================================
4. VOIX (edge-tts)
=====================================================================
- NARRATEUR (au « tu », présent, phrases très courtes, tendu et naturel) : fr-FR-RemyMultilingualNeural, rate +8 %, phrase par phrase, pitch varié -2/+2 Hz, compression douce, petite réverbération.
- SARAH (19 ans) : fr-FR-VivienneMultilingualNeural, rate +5 %.
- L'INTERPHONE (plan 2) : fr-FR-HenriNeural rate -10 %, filtre passe-bande 300-3400 Hz + grésillement.
- L'EMPLOYÉ : fr-FR-HenriNeural rate -15 %, pitch +3 Hz (voix trop polie, trop douce).
- PLAN 10 : « Merci d'être passée… » dit par la voix de Sarah (Vivienne) ralentie à -15 % et doublée par la voix de l'employé décalée de 40 ms → on entend que c'est faux.
- Ducking du fond -9 dB sous les voix.

=====================================================================
5. SONS ET MUSIQUE
=====================================================================
Fabrique-les si sources/sons/ est vide (et dis-moi lesquels) :
- Fond : bourdonnement électrique des néons + moteur de voiture au ralenti, très bas, en continu jusqu'au plan 12.
- Musique : drone sombre qui monte du plan 1 au plan 11 (-30 → -16 dB), une petite mélodie de jingle publicitaire désaccordée et lente au loin (plans 2-6). Pendant la fuite (12-13) : basse qui pulse + respiration haletante. Plan 14-15 : silence presque total, vent. Plan 15 : coups sur une vitre, étouffés.
- Grésillement d'interphone (2), imprimante thermique (5, 16), rideau de fer qui claque (7), vibration + SMS (8), choc (11, 15), moteur qui hurle + bois qui casse (12), riser 2 s + silence 0,5 s avant les plans 11 et 15.
- Mixage -14 LUFS, crête -1 dBTP.

=====================================================================
6. SCRIPT (≈ 1 min 40) — n° · clip · voix
=====================================================================
1 · V01 · badge · NARRATEUR : « Imagine, à 4 h 04, tu passes au drive… et l'interphone connaît déjà ton prénom. »
2 · V02 · INTERPHONE : « Bonsoir Sarah. Comme d'habitude ? »
3 · V03 · SARAH : « …Je suis jamais venue ici. » / INTERPHONE : « Avancez au premier guichet. »
4 · V04 · L'EMPLOYÉ : « Votre ticket, Sarah. »
5 · V05 + TICKET qui s'imprime · NARRATEUR : « Ton prénom. Ton adresse. » ⏸ « Tu n'as encore rien commandé. »
6 · V06 · 04:05 · L'EMPLOYÉ : « On prépare votre commande. Guichet suivant. » / NARRATEUR : « Il a tes cheveux. »
7 · V07 · rideau de fer · NARRATEUR : « Tu veux reculer. » / « Derrière toi, la file est fermée. »
8 · TÉLÉPHONE sur V07 · SMS de Maman (3 bulles).
9 · V09 · NARRATEUR : « Tu n'es pas rentrée. » ⏸ « Alors qui est dans ta chambre ? »
10 · V10 · 04:06 · NARRATEUR : « Au guichet trois… à côté de lui… » ⏸ « il y a toi. » / LA COPIE (voix doublée) : « Merci d'être passée. On avait juste besoin de votre place. »
11 · V11 · riser → silence → CHOC · NARRATEUR : « Le dernier guichet s'ouvre. »
12 · V12 (0-2 s) · NARRATEUR (rapide) : « Tu fonces. »
13 · V13 · HUD « LA ROUTE » · NARRATEUR : « Tu ne t'arrêtes pas. Pas une seule fois. »
14 · V14 · 04:30 · HUD « CHEZ TOI » · NARRATEUR : « Quatre heures et demie. Tu es devant chez toi. » / « La lumière de ta chambre est allumée. »
15 · V15 (0-4 s) · riser → silence → coups étouffés sur la vitre · NARRATEUR : « À la fenêtre… tu te vois. » / « Tu pleures. Tu cognes à la vitre. Tu appelles à l'aide. » ⏸ « Alors… » ⏸ « qui conduit la voiture ? »
16 · V05 (ticket) · imprimante · la ligne rouge « COMMANDE LIVRÉE ✓ » s'imprime · QUESTION FINALE · fin sur le son de l'imprimante qui s'arrête.

=====================================================================
7. VÉRIFICATION
=====================================================================
Planche de contrôle (une image toutes les 2 s) → sortie/controle_v1.jpg : pas de bande noire, textes lisibles et dans les zones sûres, V12 ≤ 2 s, V15 ≤ 4 s, ticket lisible. Voix/sous-titres synchronisés. -14 LUFS ±1. Durée 1 min 35 à 1 min 50. Résumé simple de ce qui est fait et des sons fabriqués. Ne publie rien.
```
