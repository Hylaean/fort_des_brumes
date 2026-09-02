# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Nature du dépôt

Dossier de conception d'un **jeu vidéo d'action à salles** (*action room*) en cours de création :
le joueur progresse étage par étage dans une prison-forteresse circulaire, salle par salle et
épreuve par épreuve.

**Il n'y a pas encore de code, de moteur, de build, de tests ni de lint.** Le dépôt ne contient
aujourd'hui que du Markdown et des images de référence. Ne pas chercher de `package.json`, de
projet Unity/Godot ou de suite de tests : ils n'existent pas encore. Les seules commandes utiles
sont celles de git.

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
2. Un `README.md` par section (`personnages/`, `niveaux/`, `epreuves/`, `references/`) qui sert
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
- Croquis préfixés d'un numéro d'ordre : `references/07-plan-circulaire-3.jpeg`.
- Liens entre documents toujours **relatifs** (`../references/01-sol-lave.jpeg`).
- Une fiche qui possède un croquis l'intègre en haut, juste après le titre :
  `![Croquis de l'épreuve](../references/01-sol-lave.jpeg)`.

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

`concept/references/` contient les dix-huit croquis de travail fournis dans la conversation
d'origine. `concept/generated/` archive séparément les vingt-neuf visuels générés pendant le chat,
classés par forteresse, identité, personnages, niveaux et épreuves ; son `README.md` sert de galerie
et conserve l'ordre des variantes. Le dépôt est public : vérifier la provenance avant d'ajouter de
nouvelles images.
