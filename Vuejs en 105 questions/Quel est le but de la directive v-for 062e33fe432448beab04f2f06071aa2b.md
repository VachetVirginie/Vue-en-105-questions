# Quel est le but de la directive v-for ?

Relue ?: No

La directive v-for intégrée nous permet de parcourir les éléments d'un tableau ou d'un objet.

 Vous pouvez itérer sur chaque élément du tableau ou de l'objet.

1. **Utilisation de la baie :**

```jsx
<ul id="list">
  <li v-for="(item, index) in items">
    {{ index }} - {{ item.message }}
  </li>
</ul>

var vm = new Vue({
  el: '#list',
  data: {
    items: [
      { message: 'John' },
      { message: 'Locke' }
    ]
  }
})
```

Vous pouvez aussi utiliser `of`comme délimiteur au lieu de `in`, similaire aux itérateurs javascript.

1. **Utilisation de l'objet :**

```jsx
<div id="object">
  <div v-for="(value, key, index) of user">
    {{ index }}. {{ key }}: {{ value }}
  </div>
</div>

var vm = new Vue({
  el: '#object',
  data: {
    user: {
      firstName: 'John',
      lastName: 'Locke',
      age: 30
    }
  }
})
```