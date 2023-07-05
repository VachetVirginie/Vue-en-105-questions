# Comment utilisez-vous la directive v-for sur le modèle?

Relue ?: No

Tout comme la directive v-if sur le modèle, vous pouvez également utiliser un `<template>`tag avec la directive v-for pour rendre un bloc de plusieurs éléments.

Prenons un exemple de todo,

```jsx
<ul>
  <template v-for="todo in todos">
    <li>{{ todo.title }}</li>
    <li class="divider"></li>
  </template>
</ul>
```