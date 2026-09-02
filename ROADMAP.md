# Feuille de route

Fort des Brumes avance **par jalons, sans dates**. Un jalon est terminé quand tous ses points sont
cochés et que sa phrase « fini quand » est vraie. L'ordre à l'intérieur d'un jalon est libre.

Une flèche **→** signale un point qui attend une décision du chef de projet.

## Jalon 0 — Le dossier concept *(en cours)*

- [x] Fiches des personnages, des niveaux et des épreuves
- [x] Croquis, maquette et visuels archivés dans `concept/images/`
- [x] Premier brainstorm de salles dans `concept/propositions/`
- [ ] → Trier les trente propositions : garder, modifier, barrer
- [ ] → Répondre aux six questions de structure (seul ou à plusieurs, ce qu'on gagne dans une
      épreuve, rôle des personnages, niveau sous le fort, salle du Père Nendaz, défaite)
- [ ] → Trancher les points ouverts de `concept/decisions-et-questions.md`
- [ ] → Nommer les épreuves de glace du niveau 3

**Fini quand** : chaque niveau a ses salles nommées et chaque salle a une fiche.

## Jalon 1 — Vérifier la technique

Trois essais courts, chacun répond à une question avant qu'on y passe du temps.

- [x] Moteur choisi : Godot 4 — [ADR-0001](technique/adr/0001-moteur-godot-4.md)
- [x] Langage : C# — [ADR-0002](technique/adr/0002-langage-csharp.md)
- [ ] **Essai moteur** — « Le sol, c'est de la lave » en arène circulaire : sauter de bloc en
      bloc, la lave tue, un bloc mobile, compteur de trois tours ; clavier et manette
- [ ] **Essai assets** — un croquis (Double Mine) → modèle 3D → Blender → rig → Godot
- [ ] **Essai voix** — une réplique du Cuistot en trois versions (voix enregistrée, voix
      transformée, synthèse) ; choisir à l'oreille
- [ ] Décider où vivent les fichiers lourds : Git LFS ou dépôt séparé — ADR
- [ ] Décider la chaîne croquis → 3D — ADR

**Fini quand** : on joue trente secondes dans la salle de lave avec un personnage sorti d'un croquis.

## Jalon 2 — Le prototype jouable

- [ ] Projet Godot dans son dossier à la racine du dépôt
- [ ] Personnage : déplacement, saut, caméra, mort et retour au départ
- [ ] Kit modulaire de secteur (sol, mur, porte, arche, tour centrale) instancié en cercle
- [ ] Niveau 4 complet : blocs stables, instables, explosifs et mobiles ; manettes ; mur qui
      sépare la lave de la tour
- [ ] Portes et passage d'une salle à l'autre
- [ ] Écran-titre avec le rhinocéros et le lettrage
- [ ] Français par défaut, textes prêts pour d'autres langues

**Fini quand** : quelqu'un d'extérieur finit le niveau 4 à la manette sans qu'on lui explique.

## Jalon 3 — La tranche verticale

Dix minutes de jeu qui ressemblent au jeu final.

- [ ] Rez-de-chaussée : les deux antichambres, la salle du trésor, les deux rhinocéros
- [ ] Niveau 2 : une salle de personnage au choix et une épreuve
- [ ] Un personnage modélisé, animé et doublé
- [ ] Musique : un thème glace, un thème lave, fondu de l'un à l'autre selon la salle
- [ ] Effets de lave, de glace et de brume
- [ ] → Style visuel arrêté (toon, contours, palette)
- [ ] Premier teaser vidéo à partir de captures du jeu

**Fini quand** : on montre les dix minutes à quelqu'un et il demande la suite.

## Jalon 4 — Tout le contenu

- [ ] Tous les niveaux : rez-de-chaussée, 2, 3, 4 — et le sous-sol s'il est validé
- [ ] Les dix personnages modélisés, animés et doublés
- [ ] Toutes les épreuves retenues
- [ ] Bruitages
- [ ] Sauvegarde de la progression

**Fini quand** : on peut jouer du début au trésor.

## Jalon 5 — Finitions et sortie

- [ ] Versions Mac et Windows testées sur d'autres machines que la nôtre
- [ ] Options : volume, plein écran, touches
- [ ] Bande-annonce
- [ ] → Où publier le jeu
- [ ] → Autres plateformes
