# Que sont les directives personnalisées ?

Relue ?: No

Les directives personnalisées sont de petites commandes que vous pouvez attacher aux éléments DOM.  Ils sont préfixés par v- pour faire savoir à la 
bibliothèque que vous utilisez un peu de balisage spécial et pour garder
 la syntaxe cohérente.  Ils sont généralement utiles si vous avez besoin
 d'un accès de bas niveau à un élément HTML pour contrôler un peu de 
comportement.

Créons une directive de focus personnalisée pour mettre l'accent sur un élément de 
formulaire spécifique pendant le chargement de la page,

```jsx
// Register a global custom directive called `v-focus`
Vue.directive('focus', {
  // When the bound element is inserted into the DOM...
  inserted: function (el) {
    // Focus the element
    el.focus()
  }
})
```

Vous pouvez maintenant utiliser la directive v-focus sur n'importe quel élément comme ci-dessous,

```jsx
<input v-focus>
```