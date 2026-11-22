# 🎡 LA ROUE – légendes urbaines qui font vraiment peur

⬅️ [Retour à l'accueil](../README.md)

> **Le concept :** à chaque épisode, une roue tourne et tombe sur une **légende urbaine**. Tu la vis au « tu », avec un compte à rebours, des choix à faire, et **la mort à chaque mauvais choix**. Puis la roue recule, et tu recommences avec la bonne règle.
> **Style :** personnages très simples, décors sombres et épurés, **tout en clips animés** (aucune image figée), un plan toutes les 3 à 4 s.

---

## 📺 LES ÉPISODES
| # | Légende | Origine | Statut | Ouvrir |
|---|---|---|---|---|
| 01 | **Le Bonhomme Sept-Heures** | Québec | ✅ 17 clips générés ([rendus](ep01_bonhomme_sept_heures/rendus/)) · ⬜ montage | [📝 Script](ep01_bonhomme_sept_heures/script.md) · [▶️ Plan de génération](ep01_bonhomme_sept_heures/PROMPTS_A_COLLER.md) |

---

## La formule (60 à 75 s)
| Temps | Bloc | Contenu |
|---|---|---|
| 0–3 s | **La roue** | Bruit de cliquet, la roue ralentit et s'arrête sur la légende. Phrase rituelle fixe : **« La roue tourne… et ce soir, tu devras faire face à… [nom de la légende]. »** (« à » devient « au » devant un nom masculin : « faire face au Bonhomme Sept-Heures », mais « faire face à la Dame blanche ») |
| 3–8 s | **La règle** | Le nom de la légende + sa règle en UNE phrase, de préférence un paradoxe ou une menace claire |
| 8–14 s | **Le cadre** | Une situation du quotidien, un proche avec un prénom, l'heure dans le HUD |
| 14–25 s | **La menace** | Elle arrive vite, et elle est montrée de plus en plus près |
| ~25 s | **Choix 1** | Deux boutons 1 / 2 à l'écran |
| 25–35 s | **Mauvais choix → « TU ES MORT. »** | Écran rouge, glitch, la leçon en une phrase |
| 35–40 s | **◀◀ La roue recule** + carte **« VRAI »** | Ce que dit vraiment la légende |
| 40–60 s | **Bon choix**, puis **choix 2** (même mécanique, plus court) | La tension monte encore |
| 60–75 s | **Retournement final** | Ça recommence ou ça empire, et une question au spectateur |

## Ce qui nous distingue des autres chaînes
- **Notre phrase rituelle** et **notre roue** (design à nous), avec **« ◀◀ la roue recule »** comme mécanique de seconde chance.
- **Notre héros** : tête ronde **crème** avec deux points noirs, **sweat jaune moutarde** (pas de tête noire).
- **Plus terrifiant** : la créature apparaît **de plus en plus près à chaque plan**, et chaque épisode a au moins un **jump scare** (silence, puis choc sonore et visuel).
- **Des légendes urbaines francophones** en priorité : Québec, France, Belgique, Afrique du Nord.

## Production au moins cher (testé le 22/11)
| Quoi | Modèle | Coût |
|---|---|---|
| Images de départ sans personnage | `kling-image-v3_0`, 1k | 1 crédit |
| Images de départ avec personnage | test d'abord `kling-image-v3_0` + fiche en référence ; sinon `gemini-3.1-flash-image` | 1 ou 10 crédits |
| **Clips** | **`kling-video-v2_5`, 720p, 5 s, sans audio** | **15 crédits** (3 crédits/s) |
| La roue, le HUD, les cartes, « TU ES MORT », les boutons de choix | **faits au montage** | 0 |

**Budget visé par épisode : 250 à 350 crédits.**
