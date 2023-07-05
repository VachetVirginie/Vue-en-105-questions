# Comment personnalisez-vous la directive de modèle pour un composant ?

Relue ?: No

La directive v-model sur un composant utilise  **la valeur**  comme accessoire et  **l'entrée**  comme événement, mais certains types d'entrée tels que `checkboxes`et `radio buttons`peut
 avoir besoin d'utiliser l'attribut value pour une valeur côté serveur. 
 Dans ce cas, il est préférable de personnaliser la directive de modèle.

Prenons un exemple de composant de case à cocher,

```jsx
Vue.component('custom-checkbox', {
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    checked: Boolean
  },
  template: `
    <input
      type="checkbox"
      v-bind:checked="checked"
      v-on:change="$emit('change', $event.target.checked)"
    >
  `
})
```

Vous pouvez maintenant utiliser v-model sur ce composant personnalisé comme ci-dessous,

```jsx
<custom-checkbox v-model="selectFramework"></custom-checkbox>
```

La propriété selectFramework sera transmise à l'accessoire coché et la même propriété sera mise à jour lorsque le composant de case à cocher personnalisé 
émet un événement de changement avec une nouvelle valeur.