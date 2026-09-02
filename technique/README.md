# Technique

Ce dossier rassemble les choix techniques du projet. Le code du jeu viendra plus tard dans son
propre dossier ; ici ne vivent que les décisions et leurs raisons.

## Décisions (ADR)

Chaque choix structurant fait l'objet d'un *Architecture Decision Record* numéroté dans
[`adr/`](adr/) : le contexte au moment du choix, la décision, les options écartées et les
conséquences. Un ADR ne se réécrit pas : s'il est remis en cause, un nouvel ADR le remplace et
l'ancien passe au statut « remplacé ».

| N° | Décision | Statut |
|---|---|---|
| [0001](adr/0001-moteur-godot-4.md) | Moteur de jeu : Godot 4 | accepté |

## À décider

Ces sujets ont été discutés et attendent un essai concret avant d'être tranchés :

- stockage des fichiers lourds (modèles, sons, vidéos) — Git LFS ou dépôt séparé ;
- chaîne croquis → modèle 3D (génération, Blender, rig, import) ;
- voix des personnages et musique ;
- style visuel définitif (stylisé / toon).
