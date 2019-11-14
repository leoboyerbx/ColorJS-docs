# Créer une présentation

Quelle que soit la méthode d'installation choisie, vous devriez avoir un fichier HTML qui ressemble à ça:

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

    <script src="./chemin_vers_le_script.js"></script>
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

Normalement vous avez maintenant quelque chose sui ressemble à ça:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
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

    <script src="https://cdn.colorjs.cf/v0.8/colorjs-min.js"></script>
</body>
</html>
```

Il est temps de voir le résultat ! Ouvrez votre fichier HTML dans un navigateur et utilisez les flèches de votre clavier ou les commandes à l'écran pour changer de diapo.

> Voici votre premier diaporama ColorJS ! Vous pouvez ajouter votre propre fichier css pour modifier votre mise en page, et complexifier le contenu autant que vous le souhaitez.

## Ajouter des transitions

Pour ajouter des transitions, il faut modifier les classes de vos slides.

On modifie toujours la transition de la slide qui _arrive_, pas de la slide qui part. Par exemple, si je veux un fondu pour passer de la slide 1 à 2, je mettrai la classe `fade` **sur la slide 2**. Exemple, en modifiant notre code:

```markup
<!-- Début du fichier -->
<div id="cjs-slider">
        <div class="cjs-slide" style="background-color: #f00">
            Ma première slide
        </div>
        <div class="cjs-slide fade" style="background-color: #8e44ad">
            Ma deuxième slide
        </div>
</div>
<!-- Fin du fichier-->
```

On obtient un joli fondu entre les deux slides.

### Liste des transitions disponibles

**Rappel:** Si aucune transition n'est spécifiée, le changement d'une slide à l'autre se fera par un simple "cut".

#### Transitions de premier niveau

Les transitions de premier niveaux sont les effets de transition par défaut qui s'appliquent directement sur une slide. Par exemple:

```markup
<div class="cjs-slide fade" style="background-color: #8e44ad">
     Ma deuxième slide
</div>
```

On ajoute la classe à la suite de `cjs-slide`.

**Liste des transitions**

Pour 2 slides A et B

| Tag | Effet obtenu |
| :--- | :--- |
| `fade` | Fondu de A vers B |
| `bottom` | B pousse **légèrement** A du bas vers le haut |
| `right` | B pousse **légèrement** A de la droite vers la gauche |
| `top` | B pousse **légèrement** A du haut vers le bas |
| `left` | B pousse **légèrement** A de la gauche vers la droite |

**Exemple**

```markup
<div class="cjs-slide" style="background-color: #f00">
            Ma première slide
</div>
<div class="cjs-slide bottom" style="background-color: #8e44ad">
     Ma deuxième slide
</div>
```

Ce code produira un effet de poussée de la deuxième slide qui va _légèrement_ recouvrir la première.

#### Transitions de second niveaux

Ces effets s'ajoutent à un effet déjà existant. Utilisées seules, les classes n'ont aucune action.

**Liste des effets**

Pour 2 slides A et B

| Tag | Effet obtenu | Compatible avec |
| :--- | :--- | :--- |
| `cover` | B recouvre totalement A | `bottom`, `right`, `top`, `left` |
| `push` | B pousse totalement A | `bottom`, `right`, `top`, `left` |

**Ne pas utiliser ces effets avec `fade`**.

**Exemple**

```markup
<div class="cjs-slide" style="background-color: #f00">
            Ma première slide
</div>
<div class="cjs-slide bottom cover" style="background-color: #8e44ad">
     Ma deuxième slide
</div>
```

Ce code produira un effet de poussée de la deuxième slide qui va _totalement_ recouvrir la première.

## Animation personnalisée

Imaginons que vous ayez deux éléments dans la même slide, mais vous ne voulez pas que le deuxième apparaisse tout de suite, vous voulez qu'il apparaisse quand vous cliquez. Pour cela, on va utiliser l'attribut `cjs-animate`.

### Effet prédéfini

ColorJS est fourni avec des effets prédéfinis pour l'animation personnalisée. Par exemple le code suivant dans une slide :

```markup
Contenu de ma slide
<span class="fade" cjs-animate="1">Contenu caché au dépert</span>
```

Cela produira une apparition en fondu du `span` lors du premier clic. En effet la classe `fade` est fournie avec ColorJS et définit un effet de fondu. L'attribut `cjs-animate="1"` définit que l'élément va apparaitre au premier clic. Si vous changez sa valeur pour 2, par exemple, il apparaitra au deuxième clic.

#### Liste des effets prédéfinis

| Tag | Effet produit |
| :--- | :--- |
| `fade` | Apparition de l'élément en fondu |
| `simple` | Apparition de l'élément en fondu avec un effet de translation depuis la droite vers la gauche |
| `simpleleft` | Apparition de l'élément en fondu avec un effet de translation depuis la gauche vers la droite |

### Apparitions personnalisées

Il est également possible de créer vos propres effets d'apparition. Pour cela il est nécéssaire de comprendre le fonctionnement de ColorJS:

* Lorsqu'un élément n'est pas encore affiché, il n'a pas de classe particulière, à part celles définies par l'utilisateur.
* Lorsque c'est au tour de l'élément d'apparaître, le script lui ajoute la classe `current`. Ainsi les effets prédéfinis ne sont que des règles CSS avec et sans `current`

#### Créer votre effet

Pour créer un effet donc, il faut d'abord définir les règles CSS d'un élément lorsqu'il n'est pas encore visible. Nous allons ici créer un effet de fondu et de rotation. Il aura la classe `rotate`

On définit les règles lorsque l'élément est caché:

```css
.rotate {
    opacity: 0;
    transform: rotate(-200deg);
    transition: all 0.5s ease-in-out;
}
```

Puis lorsqu'il est affiché, avec la classe `current`:

```css
.rotate.current {
    opacity: 1;
    transform: rotate(0);
}
```

Maintenant on ajoute la classe correspondante à notre élément HTML, sans oublier l'attribut `cjs-animate`:

```markup
<div class="rotate" cjs-animate="1">Contenu caché au départ</div>
```

Et voilà ! Vous avaez maintenant tous les outils pour créer votre présentation !

