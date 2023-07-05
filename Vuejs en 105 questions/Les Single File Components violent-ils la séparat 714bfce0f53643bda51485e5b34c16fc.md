# Les Single File Components violent-ils la séparation des concerns?

Relue ?: No

En ce qui concerne le dernier développement de l'interface utilisateur moderne, la 
séparation des **concerns** n'est pas égale à la séparation des types 
de fichiers. 

 Il est donc préférable de diviser les couches de base de 
code en composants faiblement couplés et de les composer au lieu de 
diviser la base de code en trois énormes couches qui s'entremêlent. 

 De cette façon, les composants de fichier unique sont plus cohérents et 
maintenables en combinant le modèle, la logique et les styles dans un 
composant.
 Vous pouvez également conserver les fichiers javascript et CSS 
séparément avec des fonctionnalités de rechargement à chaud et de 
pré-compilation.

Par exemple,

```jsx
<template>
  <div>This section will be pre-compiled and hot reloaded</div>
</template>
<script src="./my-component.js"></script>
<style src="./my-component.css"></style>
```