# Comment implémentez-vous le modèle sur les composants d'entrée personnalisés ?

Relue ?: No

Les événements 
personnalisés peuvent également être utilisés pour créer des entrées 
personnalisées qui fonctionnent avec v-model.  Le `<input>`à l'intérieur du composant doit suivre les règles ci-dessous,

1. Liez l'attribut de valeur à un accessoire de valeur
2. En entrée, émet son propre événement d'entrée personnalisé avec la nouvelle valeur.

Prenons un composant d'entrée personnalisé comme exemple,

```jsx
Vue.component('custom-input', {
  props: ['value'],
  template: `
    <input
      v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)"
    />
  `
})
```

Maintenant, vous pouvez utiliser `v-model`avec ce composant,

```jsx
<custom-input v-model="searchInput"></custom-input>
```