# Comment enregistrez-vous les directives localement ?

Relue ?: No

Vous pouvez également enregistrer des directives localement (en dehors de 
globalement) en utilisant l'option directives dans le composant comme 
ci-dessous,

```jsx
directives: {
  focus: {
    // directive definition
    inserted: function (el) {
      el.focus()
    }
  }
}
```

Vous pouvez maintenant utiliser la directive v-focus sur n'importe quel élément comme ci-dessous,

```jsx
<input v-focus>
```