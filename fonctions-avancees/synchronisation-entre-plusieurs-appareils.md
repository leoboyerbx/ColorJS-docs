# Synchronisation entre plusieurs appareils

Afin d'utiliser un téléphone ou un autre ordinateur comme télécommande, il est possible de connecter la page à un serveur de synchronisation. Ainsi lorsqu'on change de diapositive sur un appareil, l'autre appareil change aussi.

## Principe

Chaque diaporama ColorJS avec la synchronisation activée possède un identifiant de synchronisation unique. Lorsque vous activez la synchronisation, il s'identifie avec cet identifiant et tous les clients ayant le même identifiant seront synchronisés entre-eux.

## Activer la synchronisation

Pour activer la synchronisation d'un diaporama ColorJS, ajoutez un attribut dans l'élément `cjs-slider`:

* `cjs-sync-id`: avec un identifiant de synchronisation généré sur un site comme[ UUID Generator](https://www.uuidgenerator.net/)

**OU**

* `cjs-sync`: Sans valeur. L'identifiant sera alors généré automatiquement avec le contenu de la page

### Première option: un identifiant choisi arbitrairement

Si vous choisissez la première option, votre code ressemblera à ceci:

```markup
<div id="cjs-slider" cjs-sync-id="a3a8eef5-3734-4910-86a7-880dd665676b">
    <div class="cjs-slide" style="background-color: #f00">
        Ma première slide
    </div>
    <div class="cjs-slide" style="background-color: #8e44ad">
        Ma deuxième slide
    </div>
</div>
```

Sachant que l'identifiant dans l'attribut cjs-sync-id sera différent d'un diaporama à l'autre, vous pouvez en générer un sur [UUID Generator](https://www.uuidgenerator.net/).

{% hint style="danger" %}
Il est **très important** que l'identifiant soit spécifique à votre diaporama: sinon vous risquez d'interférer avec d'autres utilisateurs.
{% endhint %}

### Deuxième option: un identifiant généré automatiquement

Si vous choisissez la deuxième option, pas besoin de vous préoccuper de la génération de l'identifiant:

```markup
<div id="cjs-slider" cjs-sync>
    <div class="cjs-slide" style="background-color: #f00">
        Ma première slide
    </div>
    <div class="cjs-slide" style="background-color: #8e44ad">
        Ma deuxième slide
    </div>
</div>
```

Le script va générer automatiquement un identifiant de synchronisation en se basant sur le contenu de votre diaporama

{% hint style="danger" %}
Si vous choisissez cette option, le code de votre diaporama doit être **rigoureusement identique** d'un appareil à l'autre, sinon la synchronisation ne fonctionnera pas. À ce titre, l'utilisation de la première méthode est plus sécurisée dans le cas de modifications mineures de dernière minute.
{% endhint %}

## Utilisation

Une fois la synchronisation activée, vous verrez apparaître un nouveau bouton dans la barre de contrôle:

![](../.gitbook/assets/image%20%281%29.png)

Il permet de mettre en marche la synchronisation.

Il vous faut alors ouvrir la même présentation sur un autre appareil \(soit en copiant le dossier, soit en hébergeant votre diaporama sur un serveur\) et cliquer sur ce bouton sur les deux appareil. Vous pourrez alors contrôler le diaporama à distance.

