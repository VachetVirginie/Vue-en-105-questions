# Que sont les composants récursifs ?

Relue ?: No

Les composants qui peuvent s'invoquer de manière récursive dans leur propre modèle sont appelés composants récursifs.

```jsx
Vue.component('recursive-component', {
  template: `<!--Invoking myself!-->
             <recursive-component></recursive-component>`
});
```

Les composants 
récursifs sont utiles pour afficher des commentaires sur un blog, des 
menus imbriqués ou tout ce dont le parent et l'enfant sont identiques, 
même avec un contenu différent.

**Remarque :**  rappelez-vous que le composant récursif peut entraîner des boucles infinies avec `max stack size exceeded`erreur, assurez-vous donc que l'invocation récursive est conditionnelle (par exemple, la directive v-if).