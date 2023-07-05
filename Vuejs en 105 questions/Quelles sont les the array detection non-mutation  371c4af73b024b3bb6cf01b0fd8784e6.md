# Quelles sont les the array detection non-mutation methods?

Relue ?: No

Les méthodes qui ne modifient pas le tableau d'origine mais renvoient toujours un nouveau tableau sont appelées méthodes sans mutation.

Vous trouverez ci-dessous la liste des méthodes sans mutation,

1. filter()
2. concat()
3. slice()

Par exemple, prenons une liste de tâches où elle remplace l'ancien tableau par un nouveau basé sur le filtre d'état,

```jsx
vm.todos = vm.todos.filter(function (todo) {
  return todo.status.match(/Completed/)
})
```

Cette approche ne restituera pas la liste entière en raison de l'implémentation de VueJS.