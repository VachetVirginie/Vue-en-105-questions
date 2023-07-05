# Pourquoi ne pas utiliser les directives if et for ensemble sur le même élément?

Relue ?: No

Il est recommandé de ne pas utiliser v-if sur le même élément que v-for.  Parce que la directive v-for a une priorité plus élevée que v-if.

Il y a deux cas où les développeurs essaient d'utiliser cette combinaison,

1. Pour filtrer les éléments d'une liste

Par exemple, si vous essayez de filtrer la liste à l'aide de la balise v-if,

```jsx
  <ul>
    <li
      v-for="user in users"
      v-if="user.isActive"
      :key="user.id"
    >
      {{ user.name }}
    <li>
  </ul>
```

Cela peut être évité en préparant la liste filtrée en utilisant la propriété calculée sur la liste initiale

```jsx
  computed: {
    activeUsers: function () {
      return this.users.filter(function (user) {
        return user.isActive
      })
    }
  }
  ...... //
  ...... //
  <ul>
    <li
      v-for="user in activeUsers"
      :key="user.id">
      {{ user.name }}
    <li>
  </ul>
```

1. Pour éviter d'afficher une liste si elle doit être masquée

Par exemple, si vous essayez de vérifier conditionnellement si l'utilisateur doit être affiché ou masqué

```jsx
  <ul>
    <li
      v-for="user in users"
      v-if="shouldShowUsers"
      :key="user.id"
    >
      {{ user.name }}
    <li>
  </ul>
```

Cela peut être résolu en déplaçant la condition vers un parent en évitant cette vérification pour chaque utilisateur

```jsx
  <ul v-if="shouldShowUsers">
    <li
      v-for="user in users"
      :key="user.id"
    >
      {{ user.name }}
    <li>
  </ul>
```