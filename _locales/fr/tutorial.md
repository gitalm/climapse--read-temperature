# _locales/fr/tutorial
# My Tutorial
## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

Dans ce tutoriel, tu vas apprendre à
1. lire la température
2. afficher et travailler avec la température sur ordinateur

## Step 2

Pour commencer, nous affichons le symbole du cœur ``||basic.montrer l'icône||`` pour vérifier que le microbit fonctionne. 

```blocks
basic.showIcon(IconNames.Heart)
```

## Step 3

Nous voulons d'abord afficher la température. 
Alors nous utilisons ``||basic.afficher texte||`` la valeur interne du capteur  ``||input.température||`` 

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
})
```

## Step 4

Dans une prochaine étape, nous voulons faire transmettre la température à l'ordinateur avec ``||serial.série écrire valeur||``.
Comme couple de valeur, nous choisissons le texte *T en °C* et ``||input.Temperatur||``.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
})
```

## Step 5

Pour avoir de meilleures valeurs, il est utile d'insérer une petite pause #
en ajoutant ``||basic.Pause||`` d'une seconde, alors 1000 millisecondes.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
    basic.pause(1000)
})
```

## Step 6

Charge maintenant le code sur ton micro:bit et ouvre ensuite la *console* pour voir les valeurs.


* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
