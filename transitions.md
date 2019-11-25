# Transitions

Vous pouvez ajouter des transitions pour passer d'une slide à l'autre.

* ColorJS est fourni avec des transitions déjà définies
* Vous pouvez créer vos propres transitions

## Utiliser les transitions fournies

Pour ajouter des transitions, il faut modifier les classes de vos slides.

On modifie toujours la transition de la slide qui _arrive_, pas de la slide qui part. Par exemple, si je veux un fondu pour passer de la slide 1 à 2, je mettrai la classe `fade` **sur la slide 2**. Exemple, en modifiant notre code:

```markup
<div id="cjs-slider">
        <div class="cjs-slide" style="background-color: #f00">
            Ma première slide
        </div>
        <div class="cjs-slide fade" style="background-color: #8e44ad">
            Ma deuxième slide
        </div>
</div>
```

{% hint style="success" %}
On obtient un joli fondu entre les deux slides.
{% endhint %}

{% embed url="https://codepen.io/leoboyerbx/pen/OJJBzpW" %}

### Liste des transitions disponibles

{% hint style="info" %}
**Rappel:** Si aucune transition n'est spécifiée, le changement d'une slide à l'autre se fera par un simple "cut".
{% endhint %}

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

{% hint style="info" %}
Ces effets s'ajoutent à un effet déjà existant. Utilisées seules, ces classes n'ont aucune action.
{% endhint %}

**Liste des effets**

Pour 2 slides A et B

| Tag | Effet obtenu | Compatible avec |
| :--- | :--- | :--- |
| `cover` | B recouvre totalement A | `bottom`, `right`, `top`, `left` |
| `push` | B pousse totalement A | `bottom`, `right`, `top`, `left` |

{% hint style="warning" %}
**Ne pas utiliser ces effets avec `fade`**.
{% endhint %}

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

### Démonstration de tous les effets de transition fournis

