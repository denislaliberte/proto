Prototypage static en drupal
===========================

## Installation
- Copier les fichiers du module le dossier de votre site, l'activer et vider
la cache

## Permission
- Le module créer une nouvelle permission 'access prototype' pour pourvoir
voir les pages et partial, il faut avoir la permission. Sur une instance de 
développement on peut attribuer ce droits à l'utilisateur annonyme.

## Pages
- Ajouter un fichier template  dans le dossier pages ex. homepage.tpl.php
- Vider la cache
- La route /prototype/homepage retourne maintenant le markup de hompage.tpl.php 


## Partials
- Ajouter un fichier tempalte dans le dossier partial ex test.tpl.php
- vider a cache
- Tout les template de pages ont maintenant une variable $test qui contien le 
markup du template partial/test.tpl.php


## Features toogle
- Ajouter un nouveau partial testb.tpl.php
- Ajouter la fonction _protToogle('asdf') au template pages/homepage.tpl.php
- Ajouter un argument get à l'ur /prototype/homepage?asdf=testb
- la fonciton _protToggle('asdf') print le contenu de testb.tpl.php
- On peut aussi utiliser la fonciton _protoToggle($key) dans un bloc conditionnel
ex 
<?php 
  if(_protoToggle('asdf')) {
    print $test;
  }
?>
Si la variable get asdf contiens la clé d'un template, ce template vas être imprimé
et la fonction vas retourner faux. Donc on peut voir comparer deux partial différent
dans la même page en changeant l'url.




