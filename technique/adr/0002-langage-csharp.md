# ADR-0002 — Langage de script : C#

- **Statut** : accepté
- **Date** : 2 septembre 2026
- **Complète** : [ADR-0001](0001-moteur-godot-4.md)

## Contexte

Godot 4 propose deux langages de script de premier rang : GDScript, propre au moteur, et C# via
.NET. L'ADR-0001 avait laissé GDScript par défaut ; la décision est revue avant le premier
prototype.

Le code sera écrit en grande partie par le développeur de l'équipe, avec l'aide d'outils
d'assistance. Le chef de projet intervient surtout dans l'éditeur — scènes, niveaux, matériaux,
réglages — plus que dans le code.

## Décision

**C#** est le langage par défaut du projet. Le projet utilise la version **.NET** de Godot 4
(`Godot 4.x .NET`) et le SDK .NET correspondant.

GDScript reste autorisé ponctuellement pour un script d'éditeur ou un outil jetable, jamais pour
la logique du jeu.

## Options considérées

### C# — retenu

- Typage statique, refactorisation sûre, erreurs détectées à la compilation.
- Outillage complet : Visual Studio Code, Rider, débogueur, tests unitaires avec l'écosystème .NET.
- Meilleures performances que GDScript pour la logique lourde.
- Bibliothèques .NET disponibles si besoin (sérialisation, réseau…).

### GDScript — écarté comme langage principal

- Plus simple à lire pour un débutant et sans compilation, intégré à l'éditeur.
- Écarté parce que le code sera écrit par le développeur, pas par le chef de projet, et que le
  typage et l'outillage de C# pèsent plus lourd sur un projet qui va grossir.

## Conséquences

- **Export web** : Godot 4 ne propose pas d'export web pour les projets C# à ce jour. La
  version navigateur mentionnée dans l'ADR-0001 n'est donc pas disponible tant que ce support
  n'existe pas. Mac, Windows et Linux ne sont pas concernés ; Android et iOS sont possibles.
- Installer la version .NET de Godot et le SDK .NET sur chaque machine de développement.
- Le dépôt gagne un `.csproj` et un `.sln` ; `bin/`, `obj/` et `.godot/` sont ignorés par git.
- Chaque modification de code demande une compilation avant de lancer la scène ; les temps
  d'itération sont un peu plus longs qu'en GDScript.
- Pour que le chef de projet puisse suivre, les scripts restent courts, nommés en français
  clair, et la logique réglable (vitesses, hauteurs de saut, temps) est exposée en propriétés
  `[Export]` modifiables dans l'éditeur plutôt qu'enfouie dans le code.
