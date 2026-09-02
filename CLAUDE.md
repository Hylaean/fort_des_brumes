# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Nature du dépôt

Dossier de conception d'un **jeu vidéo d'action à salles** (*action room*) en cours de création :
le joueur progresse étage par étage dans une prison-forteresse circulaire, salle par salle et
épreuve par épreuve.

**Le moteur est choisi — Godot 4, voir `technique/adr/0001-moteur-godot-4.md` — mais le projet
Godot n'existe pas encore.** Il n'y a ni `project.godot`, ni build, ni tests, ni lint : le dépôt ne
contient que du Markdown et des images. Les seules commandes utiles sont celles de git.
`ROADMAP.md` liste les jalons : cocher un point quand il est livré, ne pas en ajouter sans
l'accord du chef de projet.

## Règle principale : la paternité des idées

Ce projet est une **collaboration entre Jean et son fils, et c'est le fils qui mène**. Le rôle de
Claude est de **mettre en forme et de conserver** ses idées, jamais de concevoir à sa place.

- Ne pas inventer de scénario, de mécanique, de personnage, de nom de salle ou de règle qui n'a
  pas été exprimé. C'est déjà la règle du dossier (`concept/README.md`) et elle prime sur tout.
- Face à un manque, **poser la question ou l'inscrire dans `concept/decisions-et-questions.md`**
  plutôt que de combler le vide soi-même.
- Ne pas « améliorer » une idée vers quelque chose de plus adulte, plus réaliste ou plus
  conventionnel. La formulation d'origine, même naïve ou étrange, est le matériau à préserver.
- Proposer est possible, mais toujours explicitement comme une proposition à valider, jamais
  écrit directement dans les fiches comme du canon.

## Décisions techniques

Les choix techniques sont consignés en ADR numérotés dans `technique/adr/` (contexte, décision,
options écartées, conséquences), indexés dans `technique/README.md`. Un nouveau choix structurant
— langage, stockage des assets, chaîne 3D, voix — donne un nouvel ADR, jamais une note glissée
dans une fiche concept. Un ADR accepté ne se réécrit pas ; on le remplace.

## Langue

Le français est la langue de travail : documents, titres de sections, noms de fichiers, messages
de commit, et locale par défaut du jeu. Écrire en français par défaut, y compris les nouveaux
documents et les réponses.

## Règles de canon

Beaucoup de décisions sont **encore ouvertes**. Le dossier assume cet état plutôt que de le masquer.

- **La correction la plus récente prime** sur les versions antérieures.
- Une idée remplacée n'est pas supprimée : elle est déplacée dans une section **`## Historique`**
  (ou *Historique des révisions*) en bas du document concerné, avec la raison du changement.
- Toute ambiguïté non tranchée va dans `concept/decisions-et-questions.md`, sous **Points à
  confirmer**, numérotée. Résoudre un de ces points implique de mettre à jour la fiche *et* de
  retirer l'entrée de cette liste.
- Les corrections évidentes de transcription vocale sont normalisées, mais la normalisation est
  consignée dans **Normalisations retenues** du même fichier.

## Organisation du dossier

`concept/` est le dossier de travail ; la racine ne contient que le `README.md` de présentation
publique du dépôt GitHub.

L'arborescence fonctionne comme un graphe de documents à trois niveaux :

1. `concept/README.md` — sommaire général et règles de lecture.
2. Un `README.md` par section (`personnages/`, `niveaux/`, `epreuves/`, `images/`) qui sert
   à la fois d'**index** et de porteur des **faits transversaux** à la section — relations entre
   personnages, principes de conception des cartes, structure commune des étages. Ces faits
   transversaux ne sont pas dupliqués dans les fiches individuelles.
3. Les fiches individuelles, une par personnage, niveau ou épreuve.

Conséquence : **créer une fiche implique toujours de l'ajouter à l'index de sa section**, et un
fait qui concerne plusieurs fiches appartient au README de section, pas à chaque fiche.

`concept/source/chronologie-du-chat.md` est la trace chronologique des 31 tours de la conversation
d'origine. C'est la **source** dont les fiches sont la synthèse : en cas de doute sur une intention,
c'est la référence à consulter, et elle ne se réécrit pas.

## Conventions de fichiers

- Noms en kebab-case, **sans accents** : `pere-nendaz.md`, `tempete-de-glace.md`.
- Niveaux préfixés et numérotés sur deux chiffres : `niveau-02-galerie.md`.
- Images rangées **par sujet** dans `images/<section>/`, croquis et rendus dans le même dossier :
  un dessin manuscrit porte le suffixe `-croquis`, les variantes `-v1`, `-v2`… —
  `images/niveaux/plan-circulaire-3-croquis.jpeg`, `images/epreuves/le-sol-c-est-de-la-lave-v2.png`.
- Liens entre documents toujours **relatifs** (`../images/epreuves/le-sol-c-est-de-la-lave-croquis.jpeg`).
- Une fiche qui possède un croquis l'intègre en haut, juste après le titre :
  `![Croquis de l'épreuve](../images/epreuves/le-sol-c-est-de-la-lave-croquis.jpeg)`.

## Gabarits des fiches

Les sections sont adaptées au sujet, mais suivent un schéma stable — voir
`concept/personnages/gardien-des-cles.md` et `concept/epreuves/le-sol-c-est-de-la-lave.md`
comme modèles de référence.

- **Personnage** : Rôle · Caractère · Apparence · Relations · Salle (listes à puces courtes,
  une caractéristique par puce), puis *Point ouvert* / *Nom* si nécessaire.
- **Épreuve** : Concept · Difficulté (notée `X/10`) · mécaniques propres · contraintes spatiales
  · *Direction de la carte concept* · *Historique*.

## Faits canoniques à ne pas altérer

- **Père Nendaz** s'écrit comme la station de ski suisse *Nendaz*. Les formes « Nanda », « Nonda »
  et « Mandat » sont des erreurs de transcription vocale déjà tranchées.
- L'emblème du fort est une **tête de rhinocéros casqué**, portée au dos des vêtements de
  plusieurs habitants.
- Le fort est sur une **crête**, pas au sommet : glacier à gauche, lave à droite, brume permanente
  née de leur rencontre en contrebas.
- Chaque étage s'organise en **couronne de salles autour d'une tour centrale**.
- La numérotation « niveau 3 » est **déduite**, pas confirmée.
- Personnages et salles se présentent en **cartes concept illustrées**, jamais en simples plans
  techniques vus du dessus.

## Images

`concept/images/` regroupe par sujet (forteresse, identité, personnages, niveaux, épreuves) les
dix-huit croquis et photos fournis dans la conversation d'origine et les vingt-neuf visuels rendus
pendant le chat ; son `README.md` sert d'index et conserve l'ordre des variantes. Les rendus peuvent
montrer des noms remplacés depuis (« Le Cuisio » pour le Cuistot, des salles renommées) : ils sont
un historique visuel, pas du canon — le texte des fiches prime. Le dépôt est public : vérifier la
provenance avant d'ajouter de nouvelles images.
