# Méthode de travail sur Kling AI

1. **Étape 1 – Images d'abord.** Génère chaque personnage en **image** (Kling → génération d'image) avec les prompts de la section 2. Garde la meilleure version de chacun : ce sont tes **références officielles**.
2. **Étape 2 – Images clés des scènes.** Pour chaque plan, génère d'abord l'**image de départ** (prompt "KEYFRAME"), en ajoutant la référence du personnage (fonction *Elements* / image de référence, selon ta version de Kling).
3. **Étape 3 – Animation.** Passe chaque image en **Image-to-Video** avec le prompt "MOTION". Durée 5 s (10 s seulement si indiqué).
   - Pour garder le pixel art propre : mets le curseur **Creativity / Relevance vers "Relevance"** (fidélité élevée).
   - Toujours coller le **prompt négatif** (section 1).
4. **Étape 4 – Montage (CapCut / Premiere).** Tous les **textes, barres de vie, XP, messages** s'ajoutent AU MONTAGE, jamais dans Kling (l'IA déforme le texte).
5. **Voix** : ElevenLabs (ou équivalent), une voix fixe par personnage. Les bouches pixel peuvent rester simples (2 positions), c'est cohérent avec le style.
6. **Format** : toujours **9:16 vertical**.

### Règle d'or de la cohérence
Copie **mot pour mot** la "fiche ADN" de chaque personnage dans chaque prompt où il apparaît. Ne la reformule jamais.
