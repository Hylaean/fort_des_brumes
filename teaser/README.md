# Teaser vidéo — script et prompts

> **Statut : proposition.** Le découpage, les cartons et l'accroche finale sont à valider par le
> chef de projet. Rien ici n'est du canon ; le canon reste dans `concept/`.

Un teaser de **60 secondes**, en **16:9**, monté à partir des visuels qui existent déjà dans
`concept/images/`. Il montre trois choses, dans cet ordre : **le lieu**, **les habitants**,
**les épreuves** — puis le titre.

Le teaser ne montre pas de gameplay : le jeu n'existe pas encore. Il montre le style, et
il le dit : c'est un jeu **en cours de création**.

- [Principes de style](#principes-de-style)
- [Typographie](#typographie)
- [Prompt de base](#prompt-de-base)
- [Découpage](#découpage)
- [Détail des plans](#détail-des-plans)
- [Son](#son)
- [Outils pour le générer](outils.md)

---

## Principes de style

Tout ce que le teaser montre vient des règles d'`identite-visuelle.md` et
d'`univers-et-forteresse.md` :

1. **Cartes concept illustrées**, pas de rendu réaliste : touche picturale, contours encrés,
   couleurs saturées. Les personnages apparaissent *comme des cartes* — c'est leur identité.
2. **Deux couleurs qui s'affrontent** : bleu-blanc de la glace à gauche, rouge-noir du magma à
   droite. La brume, blanche, naît entre les deux.
3. **La brume est partout.** Chaque plan en contient ; chaque transition passe par elle.
4. **Le fort est circulaire**, sur une crête, pas au sommet. Sa tour centrale est toujours visible.
5. **Le rhinocéros casqué** est l'emblème : il ouvre et ferme le teaser.
6. **Aucun texte généré par l'IA.** Les modèles vidéo déforment les lettres. Tous les cartons,
   noms et le titre sont ajoutés au montage, avec la vraie typographie.

## Typographie

Le canon : le titre est **très large**, en lettrage **manuscrit** dans l'esprit d'un **ancien
film d'action**, avec la tête de rhinocéros énervée dans une bulle à gauche et le logo en bas à
droite. L'écran-titre existe déjà : `concept/images/identite/ecran-titre.jpeg`. Le teaser
l'utilise tel quel pour le plan final — on ne le fait pas régénérer.

Pour les cartons et les noms de personnages, il faut une police qui s'accorde à ce lettrage.
Trois candidates, gratuites (licence OFL sur Google Fonts) :

| Police | Caractère | Pour |
|---|---|---|
| **Rock Salt** | Tracé brut au pinceau, irrégulier | Cartons en capitales (« SES HABITANTS ») |
| **Permanent Marker** | Marqueur épais, lisible, énergique | Noms des personnages |
| **Bangers** | Capitales de comics, très larges | Le tampon « 10/10 » de l'épreuve de lave |

Règle simple : **une seule police pour les cartons, une seule pour les noms.** Blanc cassé sur
brume ; rouge lave uniquement pour « 10/10 ».

→ Le choix final de la police est celui du chef de projet.

## Prompt de base

Tous les prompts ci-dessous commencent par ce préfixe de style, à coller tel quel. Les modèles
vidéo répondent mieux en anglais ; les cartons restent en français au montage.

```text
Illustrated concept-art style, painterly with visible brushwork and bold ink outlines,
saturated colors, icy blue-white against molten red-black, drifting white mist and steam
everywhere, dramatic rim light, cinematic 16:9, smooth slow camera, no text, no letters,
no watermark.
```

Prompt négatif (quand l'outil le permet) :

```text
text, letters, captions, watermark, logo, photorealistic, photo, blurry, flicker, extra limbs,
deformed face, duplicated character
```

Deux réglages qui comptent :

- **Image → vidéo** partout où une image existe : c'est ce qui garde le style. On ne décrit
  alors que le *mouvement*, pas l'image.
- **Image de début + image de fin** pour les deux plans « du croquis au rendu » (plans 3 et 4).

## Découpage

| N° | Temps | Plan | Source dans `concept/images/` | Carton |
|---|---|---|---|---|
| 1 | 0:00 – 0:05 | La brume se lève sur le fort | `forteresse/fort-glace-feu-v2.jpeg` | — |
| 2 | 0:05 – 0:09 | Du glacier à la lave, panoramique | `forteresse/fort-glace-feu-v1.jpeg` | UNE FORTERESSE ENTRE GLACE ET LAVE |
| 3 | 0:09 – 0:12 | Le rhinocéros, du croquis au rendu | `identite/ecran-titre-croquis.jpeg` → `identite/ecran-titre.jpeg` (recadré sur le rhinocéros) | — |
| 4 | 0:12 – 0:16 | Le plan circulaire prend vie | `niveaux/plan-circulaire-2-croquis.jpeg` → `niveaux/rez-de-chaussee-v2.jpeg` | — |
| 5 | 0:16 – 0:19 | Deux rhinocéros patrouillent dans le trésor | *texte → vidéo* | — |
| 6 | 0:19 – 0:25 | Les salles du niveau 2 s'allument une à une | `niveaux/niveau-02-v3.jpeg` | — |
| 7 | 0:25 – 0:26 | Carton | brume seule | SES HABITANTS |
| 8 | 0:26 – 0:38 | Huit cartes, huit habitants | `personnages/*.jpeg` (8 fiches) | nom de chacun |
| 9 | 0:38 – 0:43 | Deux cartes, deux alliés | `personnages/triple-pioche.jpeg`, `personnages/double-mine.jpeg` | ET DEUX ALLIÉS · noms |
| 10 | 0:43 – 0:44 | Carton | brume seule | SES ÉPREUVES |
| 11 | 0:44 – 0:50 | Magma vs Glace · Aviron sur glace · Tempête de glace | *texte → vidéo* ×3 | — |
| 12 | 0:50 – 0:55 | Le sol, c'est de la lave | `epreuves/le-sol-c-est-de-la-lave-v5.jpeg` | 10/10 |
| 13 | 0:55 – 1:00 | Titre | `identite/ecran-titre.jpeg` | EN COURS DE CRÉATION |

Durée totale : **60 secondes**. Treize plans, dont quatre à générer sans image source.

## Détail des plans

Pour chaque plan : la source, le mouvement demandé, le prompt, et ce qu'on ajoute au montage.

### 1 — La brume se lève *(5 s)*

Source : `forteresse/fort-glace-feu-v2.jpeg` (la version en crête).
Le plan commence dans le blanc. La brume se déchire et découvre le fort.

```text
[prompt de base] Start fully white with thick mist, the mist slowly parts to reveal a massive
circular fortress on a mountain ridge, a huge glacier on the left, flowing lava on the right,
steam rising where ice meets lava far below, very slow push-in toward the central tower.
```

Montage : silence, puis souffle du vent et sifflement de vapeur.

### 2 — Du glacier à la lave *(4 s)*

Source : `forteresse/fort-glace-feu-v1.jpeg`.
Panoramique lent de gauche à droite : du bleu au rouge, le fort au milieu.

```text
[prompt de base] Slow horizontal pan from left to right, starting on the towering blue-white
glacier, crossing the circular fortress on the ridge, ending on the red-black volcanic slope
with lava flows, steam and mist drifting between, the fortress stays in frame.
```

Montage : carton **UNE FORTERESSE ENTRE GLACE ET LAVE** en surimpression, apparu lettre par
lettre comme tracé à la main.

### 3 — Le rhinocéros *(3 s)*

Source : image de début `identite/ecran-titre-croquis.jpeg`, image de fin `identite/ecran-titre.jpeg`,
**toutes deux recadrées sur la tête de rhinocéros** (sans le titre).
Le trait de crayon devient peinture.

```text
[prompt de base] Morph from a rough pencil sketch of a helmeted rhinoceros head to its fully
painted version, ink lines appearing first then color filling in, mist curling around the
horn, the rhinoceros exhales a burst of steam at the end.
```

Montage : un grognement sourd et un coup de percussion à la fin.

### 4 — Le plan prend vie *(4 s)*

Source : image de début `niveaux/plan-circulaire-2-croquis.jpeg`, image de fin
`niveaux/rez-de-chaussee-v2.jpeg`.
Le plan dessiné à la main — ses douze secteurs numérotés, sa grille — devient la carte peinte.

```text
[prompt de base] A hand-drawn circular floor plan with numbered sectors around a central core,
grid lines lighting up one by one, the drawing slowly transforms into a painted map of the same
circular fortress floor, the camera tilts slightly as if the map gains depth, mist drifts over it.
```

Montage : crayon qui gratte le papier, puis un grondement profond.

### 5 — Le trésor *(3 s)* — sans image source

La salle du trésor du rez-de-chaussée, deux rhinocéros en patrouille. Pas d'image : on décrit
tout, en donnant une carte de personnage comme **référence de style** si l'outil le permet.

```text
[prompt de base] Inside a stone treasure vault at the heart of a circular fortress, piles of
treasure glinting in torchlight, two massive helmeted rhinoceroses patrol slowly in opposite
directions around the room, mist along the floor, low camera at floor level, one rhinoceros
turns its head toward the camera.
```

Montage : pas lourds, tintement d'or.

### 6 — Les salles du niveau 2 *(6 s)*

Source : `niveaux/niveau-02-v3.jpeg`.
Survol lent du plan ; les salles s'éclairent une à une : le Casino des Brumes, la cuisine, la
cellule, la chambre aux clés, le bureau aux trophées.

```text
[prompt de base] Slow aerial drift over a painted circular floor plan, rooms lighting up one
after another with a warm glow as the camera passes: a casino, a kitchen, a prison cell, a room
full of keys, an office with hunting trophies, mist pouring from the central tower.
```

Montage : un son différent par salle — jetons, casseroles, chaîne, clés, horloge. Pas de noms
à l'écran : ils viennent avec les personnages.

### 7 — Carton *(1 s)*

Brume seule (une seconde du plan 1, floutée). Carton **SES HABITANTS**.

### 8 — Huit cartes *(12 s, 1,5 s chacune)*

Sources : les huit fiches de `personnages/` — `pere-nendaz`, `gardien-des-cles`, `le-cuistot-v2`,
`la-joueuse`, `la-chasseuse`, `prisonnier-fou`, `sharkboy`, `lava-girl`.

Principe : **la carte elle-même est à l'écran**, en portrait au centre du 16:9, sur un fond de
brume floue. Elle glisse dans le cadre ; pendant une seconde et demie, l'illustration bouge
légèrement ; la carte suivante la chasse. On ne demande au modèle que ce petit mouvement — le
cadre de la carte, son nom et ses caractéristiques restent ceux de l'image.

Prompt commun, avec un détail par personnage :

```text
[prompt de base] The illustration inside a character card comes alive with subtle motion for
two seconds, the card frame and its layout stay perfectly still, only the character and the
mist move: {DÉTAIL}
```

| Personnage | `{DÉTAIL}` | Nom au montage |
|---|---|---|
| Père Nendaz | snow blowing across his mountaineer goggles, he narrows his eyes | PÈRE NENDAZ |
| Le Gardien des clés | the keys in his hand swing and clink, his thin smile widens | LE GARDIEN DES CLÉS |
| Le Cuistot | steam rises from his pot, flies circle him, he laughs silently, ladle-hand stirring | LE CUISTOT |
| La Joueuse | casino lights flicker over her face, she slides a chip across the table | LA JOUEUSE |
| La Chasseuse | red velvet and trophies behind her, she slowly turns her head toward the viewer | LA CHASSEUSE |
| Le Prisonnier fou | he grips his shovel and twitches, shadows of bars sway across the cell | LE PRISONNIER FOU |
| Sharkboy | cracks spread through the ice around him, one eye opens | SHARKBOY |
| Lava Girl | tiny flames flicker through her red hair, embers drift up, her magma armor glows | LAVA GIRL |

Montage : le nom apparaît en bas à gauche, en Permanent Marker, une frappe sèche par carte.
Le rythme accélère légèrement sur les quatre derniers.

### 9 — Deux alliés *(5 s)*

Sources : `personnages/triple-pioche.jpeg`, `personnages/double-mine.jpeg`.
Même dispositif, mais les deux cartes restent **côte à côte** et le rythme se pose.

| Personnage | `{DÉTAIL}` | Nom au montage |
|---|---|---|
| Triple Pioche | his lantern swings and its light sweeps across a hidden door, he grins | TRIPLE PIOCHE |
| Double Mine | he lifts his pickaxe onto his shoulder and holds out a letter, unimpressed | DOUBLE MINE |

Montage : carton **ET DEUX ALLIÉS** au-dessus des deux cartes, puis les noms.

### 10 — Carton *(1 s)*

Brume seule. Carton **SES ÉPREUVES**.

### 11 — Trois épreuves *(6 s, 2 s chacune)* — sans image source

Trois plans très courts, texte → vidéo, chacun réduit à son image la plus simple.

**Magma vs Glace** — un sol de magma, un mur de glace à escalader :

```text
[prompt de base] A wall of blue ice rising from a floor of glowing red magma, a small climber
clinging to the ice halfway up, steam pouring off the wall where it meets the heat, camera
tilting up along the wall.
```

**Aviron sur glace** — un chenal glacé en pente, des bâtons plantés dans des trous :

```text
[prompt de base] A narrow frozen channel climbing steeply between stone walls, a figure hauling
themselves upward by planting a wooden pole into holes carved in the stone, ice glittering,
mist rolling down the slope, camera following from behind.
```

**Tempête de glace** — la seule description validée est l'image ; on reste sobre :

```text
[prompt de base] A circular stone hall swallowed by a howling ice storm, snow and ice shards
streaking sideways, a figure leaning into the wind, everything blue-white, camera shaking slightly.
```

### 12 — Le sol, c'est de la lave *(5 s)*

Source : `epreuves/le-sol-c-est-de-la-lave-v5.jpeg`.
Le climax : un plan plus long, plus proche, plus violent.

```text
[prompt de base] Push-in over a huge circular arena flooded with lava around a walled central
tower, dark stone blocks scattered across the lava, some blocks wobble, one black block bursts
in a shower of embers, another block slides sideways as a lever is pulled, heat haze and thick
steam, the camera keeps pushing toward the far side of the ring.
```

Montage : tampon **10/10** en Bangers, rouge lave, qui claque à l'écran au moment de l'explosion.

### 13 — Titre *(5 s)*

Source : `identite/ecran-titre.jpeg`, **utilisée telle quelle** — on ne la régénère pas, les
lettres seraient déformées. Au montage : une nappe de brume passe devant l'image et se dissipe ;
un léger zoom arrière ; le rhinocéros dans sa bulle reçoit un petit sursaut.

Carton final, petit, sous le titre : **EN COURS DE CRÉATION**. Pas de date.

→ Une accroche est possible sous le titre, par exemple *« Entre la glace et la lave, il n'y a que
la brume. »* — à proposer au chef de projet, pas à imposer.

## Son

Le teaser n'a pas de voix : de la musique, des bruitages, des cartons. Cela évite de choisir
une voix avant le jalon 1 de la feuille de route.

- **Musique** : un seul morceau, en trois temps. Nappe glacée et lente (plans 1–6), pulsation
  qui monte (7–10), percussion lourde (11–12), silence et sifflement de vapeur sur le titre.
  Idéal pour tester le principe *thème glace / thème lave* : la nappe est le thème glace, la
  percussion le thème lave.
- **Bruitages** : vent, vapeur, grognement de rhinocéros, crayon sur papier, clés, casseroles,
  jetons, craquement de glace, explosion sourde. Presque tout se trouve sur Freesound ou se
  fabrique à la maison.
- **Mixage** : la brume a un son — un souffle continu, bas, présent du premier au dernier plan.
