# Où générer le teaser

Sélection d'outils pour produire le [script](README.md), avec une recommandation par étape.
Le paysage change tous les mois : les versions, tarifs et fonctions ci-dessous sont à
**revérifier au moment de s'y mettre** (état des connaissances : mi-2026).

## Ce qu'il faut à ce teaser

Treize plans, dont neuf partent d'une image existante. Les besoins qui départagent les outils :

1. **Image → vidéo** de qualité, qui respecte le style peint de l'image d'entrée.
2. **Image de début + image de fin** pour les deux plans « du croquis au rendu » (plans 3 et 4).
3. Des clips de **5 à 8 secondes** ; aucun plan n'est plus long.
4. Pouvoir relancer **plusieurs variantes** d'un même plan sans se ruiner.
5. Aucun texte à générer : il est ajouté au montage.

## Génération vidéo

| Outil | Points forts pour ce teaser | Début + fin | Son natif | Accès |
|---|---|---|---|---|
| **Kling** (klingai.com) | Image → vidéo très fidèle à la source, mouvement contrôlable, bon sur les personnages | oui | selon version | crédits bon marché, abonnement |
| **Google Veo** (Flow, Gemini, API) | Qualité et lumière excellentes, ambiances sonores générées avec l'image | selon version | oui | abonnement Google AI ou API à l'usage |
| **Luma Dream Machine** | Les images-clés début + fin sont sa spécialité : parfait pour les plans 3 et 4 | oui | non | abonnement |
| **Runway** (Gen-4) | Références pour garder un personnage cohérent, outils de retouche vidéo | selon version | non | abonnement |
| **Hailuo** (MiniMax) | Mouvement naturel, prix bas ; bonne seconde source de variantes | selon version | selon version | crédits |
| **Sora** (sora.com) | Outil de storyboard intégré, clips plus longs ; inclus dans certains abonnements ChatGPT | non | oui | abonnement ChatGPT |
| **Wan** (open source, local) | Gratuit et illimité, image → vidéo et début + fin ; demande un GPU — lent sur Mac Apple Silicon | oui | non | gratuit, via ComfyUI |

Deux façons d'y accéder qui comptent pour nous :

- **fal.ai** ou **Replicate** : les mêmes modèles (Kling, Veo, Luma, Wan…) derrière une API,
  payés au clip. Un script lance les treize plans en trois variantes chacun, et on choisit. C'est
  la voie naturelle pour un développeur, et la moins chère pour itérer.
- **Krea**, **Higgsfield**, **Freepik** : une interface, plusieurs modèles, un abonnement. Pratique
  pour tester à la main avec le chef de projet et comparer les résultats en direct.

### Recommandation

| Plans | Outil | Pourquoi |
|---|---|---|
| 1, 2, 5, 6, 11, 12 | **Kling** (ou Veo) | Image → vidéo fidèle, ambiances |
| 3, 4 | **Luma** ou Kling en mode début + fin | Transition croquis → rendu |
| 8, 9 (les cartes) | **Kling** | Garde le cadre de la carte immobile, n'anime que l'illustration |
| 13 (titre) | aucun | L'écran-titre est animé au montage, jamais régénéré |

Accès conseillé : **fal.ai** pour lancer les variantes en série, et un abonnement d'un mois à
**Kling** pour retoucher à la main les plans qui résistent.

Ordre de grandeur : 13 plans × 3 variantes ≈ 40 clips de 5 s. Au clip, cela se chiffre en
dizaines d'euros, pas en centaines — à vérifier sur la grille du moment.

## Préparer les images

Les visuels de `concept/images/` sont en portrait (environ 1100 × 1400) ; le teaser est en 16:9.

- **Plans 1, 2, 6, 12** (paysages, plans) : recadrer une bande 16:9 dans l'image et laisser la
  caméra bouger dedans. Pas de régénération : le fort reste celui du concept. Si un plan a
  vraiment besoin de plus large, agrandir les bords avec un outil d'*outpainting* (Krea, Firefly,
  Photoshop) et vérifier que rien d'inventé n'apparaît.
- **Plan 3** : recadrer le croquis et le rendu **sur le rhinocéros seul, avec le même cadrage**,
  sinon la transition saute.
- **Plans 8, 9** : ne pas recadrer. La carte reste entière, en portrait ; elle est posée sur un
  fond de brume au montage.
- Exporter chaque source en JPEG ou PNG, au moins 1920 px sur le grand côté.

## Montage

- **DaVinci Resolve** (gratuit) : montage, cartons avec les polices Google Fonts installées sur le
  Mac, surimpressions de brume, mixage son. C'est l'outil recommandé ; il servira aussi à la
  bande-annonce du jalon 3.
- **CapCut** ou **iMovie** si l'on veut aller vite avec le chef de projet.
- **Brume** : quelques boucles de fumée ou brouillard sur fond noir (banques gratuites : Pexels,
  Pixabay) en mode *Screen* par-dessus les plans, pour lier les coupes.
- **Agrandissement** (facultatif) : les clips sortent souvent en 720p ou 1080p ; Topaz Video AI
  (payant) ou Real-ESRGAN (gratuit) pour un 1080p propre.

## Son

- **Musique** : GarageBand pour composer le morceau en trois temps ; Suno ou Udio pour une
  maquette rapide, en vérifiant la licence avant toute diffusion.
- **Bruitages** : Freesound (CC0), enregistrements maison, ElevenLabs pour un effet précis.

## Livrable et rangement

- Export **1920 × 1080, H.264, 60 s**, plus une version verticale 1080 × 1920 si utile pour un
  téléphone.
- Les clips générés et le projet de montage sont lourds : ils ne vont **pas dans ce dépôt**.
  Ils suivront la décision sur les fichiers lourds (voir `technique/README.md`). Le teaser fini
  peut être mis en ligne en non répertorié et lié depuis le README.

## Étapes

1. Préparer les sources (recadrages 16:9, crops du rhinocéros).
2. Lancer trois variantes de chaque plan.
3. Choisir avec le chef de projet — c'est son teaser.
4. Monter : coupes, brume, cartons, titre.
5. Musique et bruitages.
6. Exporter, montrer, ajuster.
