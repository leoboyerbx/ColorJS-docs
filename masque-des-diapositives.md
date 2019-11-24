# Masque des diapositives

ColorJS possède un système de masque de diapositives basiques. Cela permet d'afficher un contenu récurrent sur chaque page.

## Principe

Pour cela il suffit d'ajouter un élément avec la classe `cjs-mask` et de mettre à l'intérieur ce que vous voulez voir apparaître sur chaque diapo.

## Exemple

Prenons un diaporama ColorJS très basique structuré de cette manière:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
    
    <script defer src="https://cdn.colorjs.cc/latest/colorjs.bundle.js"></script>
</head>
<body>
    <div id="cjs-slider">
        <div class="cjs-slide" style="background-color: #f00">
          <div class="slidecontent">
            Slide#1         
          </div>
        </div>
        <div class="cjs-slide cover bottom" style="background-color: #8e44ad">
          <div class="slidecontent">
            Slide#2            
          </div>
        </div>
    </div>
</body>
</html>
```

Pour que du contenu soit répliqué sur chaque slide, il suffit d'ajouter une `div`avec la classe `cjs-mask`dans l'élément `#cjs-slider`:

```markup
<div class="cjs-mask">
    Content in the mask
</div>
```

Ce qui donne:

```markup
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Titre de mon diaporama</title>
    
    <script defer src="https://cdn.colorjs.cc/latest/colorjs.bundle.js"></script>
</head>
<body>
    <div id="cjs-slider">
        <div class="cjs-slide" style="background-color: #f00">
          <div class="slidecontent">
            Slide#1         
          </div>
        </div>
        <div class="cjs-slide cover bottom" style="background-color: #8e44ad">
          <div class="slidecontent">
            Slide#2            
          </div>
        </div>
      
        <div class="cjs-mask">
          Content in the mask
        </div>
    </div>
</body>
</html>
```

Et voilà! Le contenu dans l'élément masque est répliqué sur toutes les slides lors du chargement de la page!

{% embed url="https://codepen.io/leoboyerbx/pen/zYYQqoP" %}



