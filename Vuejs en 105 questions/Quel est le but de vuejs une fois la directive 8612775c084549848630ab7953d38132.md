# Quel est le but de vuejs une fois la directive ?

Relue ?: No

Si vous voulez rendre `a lot of static content`alors
 vous devez vous assurer qu'il n'a été évalué qu'une seule fois, puis 
mis en cache par la suite.  Dans ce cas, vous pouvez utiliser `v-once`directive en enveloppant au niveau racine.

L'exemple d'utilisation de la directive v-once serait comme ci-dessous,

```jsx
Vue.component('legal-terms', {
  template: `
    <div v-once>
      <h1>Legal Terms</h1>
      ... a lot of static content goes here...
    </div>
  `
})
```

> **Remarque :**  Il est recommandé de ne pas en abuser à moins que le rendu ne soit lent en raison d'un grand nombre de contenus statiques.
>