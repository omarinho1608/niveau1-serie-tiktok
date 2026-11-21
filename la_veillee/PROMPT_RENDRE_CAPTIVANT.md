# 🔥 Prompt « rends-le captivant » pour Claude Code

⬅️ [Retour à la série](README.md)

À coller **dans ta session de montage Claude Code** (le dossier `Montage_Ankou`), **après** une première version de la vidéo. Il fonctionne pour n'importe quel épisode de La Veillée.

```text
La vidéo est trop molle : je veux qu'elle soit FLUIDE et CAPTIVANTE, qu'on ne puisse pas scroller. Tu vas retravailler le script ET le montage. Relis d'abord SUIVI.md et respecte toutes mes règles déjà notées.

ÉTAPE 1 — DIAGNOSTIC (avant de toucher à quoi que ce soit)
Regarde la dernière version dans sortie/ : extrais une image toutes les 2 s et écoute la piste audio (transcris-la si besoin). Découpe la vidéo en tranches de 5 s et donne une note d'intérêt de 1 à 5 à chaque tranche, avec la raison (« plan fixe trop long », « phrase explicative », « aucun son », « on sait déjà ce qui va arriver »…). Montre-moi ce tableau en premier, en langage simple.

ÉTAPE 2 — RÉÉCRIRE LE SCRIPT (nouveau fichier script_v3.md, ne supprime pas l'ancien)
Règles d'écriture :
- La 1re seconde doit déjà être une image qui bouge + un son fort + une phrase choc. Aucun titre, aucune présentation avant.
- Au présent, à la 1re personne. Phrases de 3 à 8 mots. Une phrase = une image ou une sensation (froid, odeur, bruit, tremblement). Zéro phrase d'explication.
- Toutes les 8 à 12 s, une « boucle ouverte » : une phrase qui promet la suite (« Ce n'était pas le pire. », « Je n'aurais jamais dû regarder. », « Il connaissait mon prénom. »).
- Chaque scène doit faire monter la tension d'un cran. Si une phrase ne fait ni peur, ni avancer l'histoire, supprime-la.
- Garde un vrai moment d'émotion (un silence, un sacrifice, un regard) avant le dernier acte.
- Fin : une dernière image qui glace + une question au spectateur. Si possible, la dernière phrase doit faire écho à la première pour donner envie de revoir la vidéo en boucle.
- Durée finale entre 1 min 15 et 1 min 50 (jamais sous 1 min). Plus court et plus dense vaut mieux que long et mou.
- Utilise en priorité les clips qui existent déjà dans clips/. Un même clip peut servir plusieurs fois (recadré, ralenti, inversé, zoomé sur un détail). Si un nouveau clip est vraiment indispensable, ne l'invente pas : écris-moi à la fin la liste des clips à générer, avec pour chacun un prompt Kling en anglais (pixel art 16-bit, nuit, brume, une seule lumière chaude, format 9:16), une image clé et une animation lente.

ÉTAPE 3 — REFAIRE LE MONTAGE (nouvelle version dans sortie/, n'écrase jamais l'ancienne)
- Jamais plus de 2,5 s sans changement à l'écran : une coupe, un zoom, un recadrage, un texte ou un mouvement. Alterne plans larges et gros plans.
- Coupe sur le mouvement. Commence chaque plan au milieu d'une action, pas au début du clip.
- Fais arriver le son AVANT l'image (le grincement commence 0,5 s avant qu'on voie la charrette) et fais déborder le son d'un plan sur le suivant pour que tout soit fluide.
- Zoom « coup de poing » rapide (105 % → 115 % en 0,15 s) sur les mots-clés et les révélations. Petit tremblement d'image sur les chocs.
- Rythme en vagues : rapide, rapide, puis un silence de 0,5 à 1 s juste avant chaque révélation, puis le choc.
- Sous-titres mot à mot, très lisibles, mot-clé en couleur, et jamais en retard sur la voix.
- Le son est la moitié de la peur. Il faut toujours une ambiance en fond (vent, grillons, feu, respiration), des bruitages précis sur chaque action, une musique qui monte doucement pendant la tension et qui s'arrête net avant le climax. Coupe tout, silence total, au moment le plus effrayant.
- La voix du narrateur doit être tendue et un peu plus rapide pendant l'action, et plus lente et basse pendant les moments d'émotion. Régénère les voix si besoin.
- Aucune carte ou texte ne reste plus de 2,5 s, sauf la carte finale.

ÉTAPE 4 — VÉRIFICATION (obligatoire)
Refais le tableau de l'étape 1 sur la nouvelle version. Aucune tranche de 5 s ne doit être notée en dessous de 4. Si c'est le cas, corrige encore avant de me la montrer. Vérifie aussi la durée, la lisibilité des sous-titres sur des images de contrôle, et le volume (-14 LUFS).

ÉTAPE 5 — RAPPORT ET MÉMOIRE
Donne-moi en quelques lignes ce que tu as changé et pourquoi, le chemin de la nouvelle vidéo, et la liste des clips à générer s'il y en a. Ajoute dans SUIVI.md, avec la date du jour, les règles « captivant » ci-dessus qui doivent s'appliquer à toutes mes prochaines vidéos.
```
