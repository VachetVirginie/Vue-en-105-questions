# Que sont les composants asynchrones ?

Relue ?: No

Dans les grandes applications, nous devrons peut-être diviser l'application en plus 
petits morceaux et ne charger un composant du serveur que lorsque cela 
est nécessaire.  Pour ce faire, Vue vous permet de définir votre 
composant en tant que fonction d'usine qui résout de manière asynchrone 
la définition de votre composant.  Ces composants sont appelés 
composants asynchrones.

Voyons un exemple de composant asynchrone utilisant la fonction de fractionnement de code webpack,

```jsx
Vue.component('async-webpack-example', function (resolve, reject) {
  // Webpack automatically split your built code into bundles which are loaded over Ajax requests.
  require(['./my-async-component'], resolve)
})
```

Vue ne déclenchera la fonction factory que lorsque le composant doit être rendu et mettra en cache le résultat pour les futurs rendus.