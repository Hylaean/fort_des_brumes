# ADR-0001 — Moteur de jeu : Godot 4

- **Statut** : accepté
- **Date** : 2 septembre 2026

## Contexte

Fort des Brumes est un jeu d'action à salles en **3D**. Il doit tourner sur **Mac et Windows**
en priorité ; d'autres plateformes restent possibles plus tard.

Contraintes qui pèsent sur le choix :

- L'équipe est de deux personnes, dont un chef de projet enfant qui mène la création. Les outils
  doivent pouvoir être ouverts et manipulés par lui, pas seulement par le développeur.
- Le développement se fait sur Mac.
- Le dépôt est public sur GitHub : les fichiers du projet doivent être du texte lisible et
  fusionnable par git.
- Le style visuel visé est **stylisé**, fidèle aux croquis, pas réaliste.
- Besoins techniques identifiés : brume et vapeur, lave et glace, plateformes qui bougent ou
  explosent, caméra de salle, clavier et manette, français par défaut.

## Décision

**Godot 4**, dans sa dernière version stable 4.x au moment de démarrer le prototype. La version
exacte sera figée dans `project.godot` et notée ici.

Langage principal : **GDScript**, lisible par le chef de projet et intégré à l'éditeur. Le C# n'est
pas exclu pour un besoin précis ; ce serait une décision séparée.

## Options considérées

### Godot 4 — retenu

- Gratuit, licence MIT, aucune redevance.
- Éditeur natif et complet sur Mac.
- Exports Mac, Windows, Linux et web en un clic ; mobile possible.
- Scènes et ressources en fichiers texte (`.tscn`, `.tres`) : diff et fusion propres dans git.
- L'arbre de scènes correspond naturellement à « un fort → des étages → des secteurs → des salles ».
- GDScript proche de Python, abordable pour un débutant.
- Localisation intégrée (CSV ou PO).
- Mode *Movie Maker* pour capturer des bandes-annonces image par image.

### Unity — écarté

- Plus grand écosystème d'assets et de tutoriels ; C# ; gratuit sous un seuil de revenus.
- Écarté parce que plus complexe à prendre en main pour un enfant, et parce que ses fichiers de
  scène sont moins lisibles dans git par défaut. Reste l'option de repli si la boutique d'assets
  ou les consoles deviennent un vrai besoin.

### Unreal Engine 5 — écarté

- Meilleur rendu (lumière, brume volumétrique, effets de lave) ; Blueprints ludiques pour un enfant.
- Écarté parce que lourd sur Mac, projets énormes, fichiers `.uasset` binaires incompatibles avec
  un dépôt git public, et outillage pensé pour de grandes équipes.

## Conséquences

- Les exports consoles ne sont possibles qu'à travers des partenaires tiers ; ce n'est pas un
  objectif pour l'instant.
- L'écosystème d'assets est plus petit : la chaîne croquis → modèle 3D devra être définie par un
  ADR dédié après essai.
- Le rendu 3D de Godot est moins mature que celui des deux autres : vérifier tôt, sur Mac, que
  les effets de brume et de lave tiennent **60 images par seconde**. C'est l'objet du premier
  prototype.
- Le dossier `.godot/` sera ignoré par git. Les fichiers lourds (modèles, sons, vidéos) feront
  l'objet d'une décision séparée (Git LFS ou dépôt distinct).
- Clavier et manette sont configurés dans l'*Input Map* dès le premier prototype.
- Le projet Godot vivra dans un dossier dédié à la racine du dépôt, à côté de `concept/` et
  `technique/`.
