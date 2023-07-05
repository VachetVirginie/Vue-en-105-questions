# Quels sont les composants fonctionnels ?

Relue ?: No

Les composants 
fonctionnels ne sont que des fonctions simples pour créer des composants
 simples simplement en passant un contexte.  Chaque composant 
fonctionnel suit deux règles,

1. **Sans état :**
    
    il ne conserve aucun état par lui-même
    
2. **Sans instance :**
    
    il n'a pas d'instance, donc pas de this
    

Vous devez définir `functional: true`pour le rendre fonctionnel.  Prenons un exemple de composants fonctionnels,

```jsx
Vue.component('my-component', {
  functional: true,
  // Props are optional
  props: {
    // ...
  },
  // To compensate for the lack of an instance,
  // we are now provided a 2nd context argument.
  render: function (createElement, context) {
    // ...
  }
})
```

> **Remarque :**  Les composants fonctionnels sont également très populaires dans la communauté React.
>