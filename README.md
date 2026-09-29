# Fléchettes 🎯

Application pour compter les points d'une partie de fléchettes sur téléphone.
Simple, sans compte, sans publicité, et qui marche même sans connexion.

**Utiliser l'application : https://bartras.github.io/cricket_claude/**

## Fonctionnalités

- **Trois modes de jeu** : Cricket, 301 et La course folle.
- **2 à 6 joueurs**, avec des noms personnalisables (mémorisés d'une partie à l'autre).
- **Saisie fléchette par fléchette** : Simple, Double ou Triple, puis le numéro touché. Bouton « Raté » (×2 et ×3 pour rater plusieurs fléchettes d'un coup).
- **Annuler** autant de fléchettes que nécessaire, y compris après une victoire.
- **Joueur suivant** automatique après 3 fléchettes (ou à la main).
- **Statistiques de fin de partie** et **feu d'artifice** pour le gagnant.
- **Partie sauvegardée** automatiquement : on peut fermer l'app et reprendre plus tard.
- **Écran toujours allumé** pendant la partie, vibrations, interface pensée pour une main.

## Les modes

### Cricket
- Cibles : 20, 19, 18, 17, 16, 15 et Bull.
- Une cible est *fermée* après 3 marques (simple = 1, double = 2, triple = 3).
- Une fois la cible fermée, chaque marque supplémentaire rapporte des points, tant qu'au moins un adversaire ne l'a pas fermée.
- Gagne celui qui a fermé toutes les cibles avec un score supérieur ou égal à celui des autres.
- Stats : score, marques par tour, fléchettes, doubles, triples, ratés.

### 301
- Chacun part de 301 et descend jusqu'à exactement 0.
- Option au démarrage : **finir par un double** (le Bull compte comme un double) ou **fin libre**.
- **Bust** : si tu dépasses 0, tombes à 1 (avec double obligatoire), ou finis sans double quand il en faut un, le tour est annulé et le score revient à celui du début du tour.
- **Aide à la finition** : l'app propose les fléchettes à jouer pour finir (ex. `T20 · T15 · D8`, T = triple, D = double), pour le joueur en cours et pour chaque joueur.
- Stats : reste, moyenne par tour, fléchettes, doubles, triples, ratés, busts.

### La course folle
Un mode inventé pour s'amuser.
- Il faut atteindre le **Bull** en partant de **1** : 1, 2, 3 … 20, puis Bull.
- À chaque tour (3 fléchettes), toucher son chiffre fait avancer d'une case.
- **Double** : on avance de 2 (un chiffre sauté). **Triple** : on avance de 3 (deux chiffres sautés).
- Seul le résultat **à la fin des 3 fléchettes** compte, l'ordre n'a pas d'importance (sur le 1, toucher 3 puis 1 puis 2 fait avancer jusqu'au 4).
- **Bonus** : si les 3 fléchettes ont toutes servi à avancer, on saute un chiffre de plus pour le tour suivant.
- Le Bull ne se saute pas : il faut le toucher. Le premier qui y arrive gagne.
- Un résumé des règles est consultable avant de lancer la partie (affiché quand ce mode est sélectionné).

## Installer sur son téléphone

L'application est une **PWA** : elle s'installe depuis le navigateur, sans passer par un magasin d'applications.

- **Android (Chrome, Brave…)** : ouvrir le lien, menu ⋮ puis *Installer l'application* (ou *Ajouter à l'écran d'accueil*).
- **iPhone** : ouvrir le lien dans **Safari**, bouton Partager puis *Sur l'écran d'accueil*.

Les mises à jour arrivent toutes seules : il suffit de fermer et rouvrir l'app.
Les données (noms, partie en cours) restent sur le téléphone, rien n'est envoyé sur Internet.

## Pour les développeurs

Pas de framework ni de compilation : du HTML, CSS et JavaScript simples.

| Fichier | Rôle |
| --- | --- |
| `index.html` | Toute l'application (interface, règles, statistiques) |
| `manifest.webmanifest` | Nom, couleurs et icônes pour l'installation |
| `sw.js` | Service worker : fonctionnement hors connexion |
| `icons/` | Icônes de l'application |

Pour tester en local, servir le dossier avec un petit serveur, par exemple :

```
python3 -m http.server 8000
```

puis ouvrir `http://localhost:8000`.

Le site est publié avec **GitHub Pages**. Après une modification importante, augmenter le numéro de version du cache dans `sw.js` (`cricket-vN`) pour forcer la mise à jour chez les utilisateurs.
