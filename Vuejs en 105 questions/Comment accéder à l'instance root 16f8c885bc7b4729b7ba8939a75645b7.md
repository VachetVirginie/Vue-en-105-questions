# Comment accéder à l'instance root ?

Relue ?: No

L'instance racine (new Vue()) est accessible avec le `$root`propriété.

Voyons l'utilisation de l'instance root avec un exemple.

Commençons par créer une instance racine avec les propriétés et les méthodes comme ci-dessous,

```jsx
// The root Vue instance
new Vue({
  data: {
    age: 26
  },
  computed: {
    fullName: function () { /* ... */ }
  },
  methods: {
    interest: function () { /* ... */ }
  }
})
```

Vous pouvez maintenant accéder aux données de l'instance racine et à ses méthodes avec des sous-composants comme ci-dessous,

```jsx
// Get root data
this.$root.age

// Set root data
this.$root.age = 29

// Access root computed properties
this.$root.fullName

// Call root methods
this.$root.interest()
```

Il est recommandé d'utiliser Vuex pour gérer l'état au lieu d'utiliser l'instance racine comme magasin global.