# Créer une présentation

Quelle que soit la méthode d'installation choisie, vous devriez avoir un fichier HTML qui ressemble à ça:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
    
    <script defer src="./chemin_vers_le_script.js"></script>
</head>
<body>
    <div id="cjs-slider">

    </div>

</body>
</html>
```

## Créer une slide

Une slide est un `div` avec la classe `cjs-slide`. Pour créer une slide on écrit donc:

```markup
<div class="cjs-slide">
    <!-- Ici le contenu de la slide -->
</div>
```

Vous pouver déjà assigner une couleur d'arrière plan à votre slide en utilisant CSS, soit dans un fichier séparé, soit directement sur la balise:

```markup
<div class="cjs-slide" style="background-color: #fa6756">
            Ma première slide
</div>
```

Vous pouvez ajouter une slide supplémentaire afin de voir les transitions:

```markup
<div class="cjs-slide" style="background-color: #8e44ad">
    Ma deuxième slide
</div>
```

Votre fichier HTML ressemble maintenant à ceci:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
    
    <script defer src="./chemin_vers_le_script.js"></script>
</head>
<body>
    <div id="cjs-slider">
        <div class="cjs-slide" style="background-color: #f00">
            Ma première slide
        </div>
        <div class="cjs-slide" style="background-color: #8e44ad">
            Ma deuxième slide
        </div>
    </div>
</body>
</html>
```

Il est temps de voir le résultat ! Ouvrez votre fichier HTML dans un navigateur et utilisez les flèches de votre clavier ou les commandes à l'écran pour changer de diapo.

> Voici votre premier diaporama ColorJS ! Vous pouvez ajouter votre propre fichier CSS pour modifier votre mise en page, et complexifier le contenu autant que vous le souhaitez.

## 

