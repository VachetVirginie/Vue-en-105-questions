# Comment communiquez-vous d'enfant à parent à l'aide d'événements ?

Relue ?: No

Si vous voulez que l'enfant veuille communiquer avec le parent, émettez un événement de l'enfant en utilisant `$emit`s'opposer au parent,

```jsx
Vue.component('todo-item', {
  props: ['todo'],
  template: `
    <div class="todo-item">
      <h3>{{ todo.title }}</h3>
      <button v-on:click="$emit('increment-count', 1)">
        Add
      </button>
      <div v-html="todo.description"></div>
    </div>
  `
})
```

Vous pouvez maintenant utiliser cet élément todo dans le composant parent pour accéder à la valeur de comptage.

```jsx
<ul v-for="todo in todos">
  <li>
    <todo-item
      v-bind:key="todo.id"v-bind:todo="todo"v-on:increment-count="total += 1"
    /></todo-item>
  </li>
</ul>
<span> Total todos count is {{total}}</span>
```