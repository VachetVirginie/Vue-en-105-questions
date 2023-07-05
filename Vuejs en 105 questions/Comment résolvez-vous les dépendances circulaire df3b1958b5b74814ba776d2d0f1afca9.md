# Comment résolvez-vous les dépendances circulaires entre les composants ?

Relue ?: No

Dans les 
applications complexes, les composants vue seront en fait le descendant 
et l'ancêtre les uns des autres dans l'arborescence de rendu.

Disons composantA et composantB inclus dans leurs modèles respectifs, ce qui crée une dépendance circulaire,

```jsx
//ComponentA
<div>
  <component-b >
</div>
```

```jsx
//ComponentB
<div>
  <component-a >
</div>
```

Cela peut être résolu en enregistrant (ou en attendant) le composant enfant dans `beforeCreate`crochet ou en utilisant l'importation asynchrone de webpack lors de l'enregistrement du composant,

**Solution1 :**

```jsx
beforeCreate: function () {
 this.$options.components.componentB = require('./component-b.vue').default
}
```

**Solution2 :**

```jsx
components: {
 componentB: () => import('./component-b.vue')
}
```