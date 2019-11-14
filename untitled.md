# Démarrer

L'installation est très simple: en effet ColorJS s'éxécute coté client. Il n'est pas nécessaire d'installer un serveur. Téléchargez simplement la dernière version sur [le dépôt officiel](https://github.com/leoboyerbx/ColorJS/releases/latest), outilisez le CDN

## Choisir le support

ColorJS est disponible sous la forme d'une archive ou via un cdn.

Si vous ne savez pas quelle méthode utiliser, voici un tableau qui récapitule les possibilités de chaque méthode

| Méthode | Téléchargement | CDN |
| :--- | :---: | :---: |
| Nombre de lignes de code à ajouter dans votre fichier | 1 | 1 |
| Ne nécessite pas d'autres fichiers que votre diaporama lui-même | ❌ | **✔** |
| Est utilisable sans connexion internet | **✔** | ❌ |
| Rapidité | **➕➕➕** | ➕ |
| Facilité de mise à jour | ❌ | **✔** |

## Avec l'archive téléchargée

La première méthode est de télécharger l'archive indiquée plus haut.

### Fichiers téléchargés

Vous obtenez dans l'archive la structure suivante:

```text
.
├── assets
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
└── index.html
```

* `example.html`: Un diaporama d'exemple déjà créé. vous pouvez l'ouvrir pour voir à quoi ressemble un diaporama déjà existant. Il est facultatif et vous pouvez le supprimer.
* `index.html`: Un fichier HTML avec les éléments de base pour commencer la création de votre diaporama.
* `force-ratio.html`: Une page qui permet d'afficher le diaporama contenu dans `index.html`, mais en conservant le ratio d'aspect 16:9 \(modifiable\).
* `dist`: ce dossier contient `bundle.js`, le script en lui-même. Vous pouvez déplacer ce fichier mais n'oubliez pas dans ce cas de mettre à jour le chemin vers `bundle.js` dans `index.html`.
* `assets`: Ce dossier contient des feuilles de style et la bobliothèque fontawesome ui sont nécessaires au fonctionnement du script. Il ne faut pas déplacer ce dossier et son contenu par rapport à `index.html`, sinon le script ne fonctionnera plus.

Vous pouvez créer le contenu de votre diaporama dans `index.html`.

## Avec le CDN

ColorJS dispose d'un CDN accessible à l'adresse [cdn.colorjs.cf](http://cdn.colorjs.cf). Il permet d'éviter d'avoir à télécharger des fichiers.

Pour l'utiliser, partez d'un fichier HTML5 standard, par exemple:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
</head>
<body>

</body>
</html>
```

Dans le body, créez un `div` qui a l'id `cjs-slider`. C'est le **Slider**, l'élément qui contiendra toutes vos _slides_ \(diapos\).

Enfin juste avant la balise `</body>`, ajoutez la ligne de code:

```markup
<script src="https://cdn.colorjs.cf/v0.8/colorjs-min.js"></script>
```

Ce qui doit donner :

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
</head>
<body>
    <div id="cjs-slider">

    </div>

    <script src="https://cdn.colorjs.cf/v0.8/colorjs-min.js"></script>
</body>
</html>
```

Vous êtes prêt à créer votre diaporama !

> **Attention:** Si vous utilisez le CDN, il faudra disposer d'une connexion internet à chaque fois que vous projetterez le diaporama, il peut être plus prudent d'utiliser la première méthode si vous avez un doute.



