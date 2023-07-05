# A quoi sert le compilateur vuejs ?

Relue ?: No

Le compilateur est responsable de la compilation des chaînes de modèle dans les fonctions de rendu JavaScript.

Par exemple, l'extrait de code ci-dessous montre la différence entre les modèles qui nécessitent un compilateur et non,

```jsx
// this requires the compiler
new Vue({
  template: '<div>{{ message }}</div>'
})

// this does not
new Vue({
  render (h) {
    return h('div', this.message)
  }
})
```