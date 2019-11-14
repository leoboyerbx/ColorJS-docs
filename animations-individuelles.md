# Animations individuelles

{% hint style="info" %}
Ces fonctionnalités correspondent à la fonctionnalité _animation personnalisée_ de LibreOffice ou du _Volet animation_ de PowerPoint
{% endhint %}

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

