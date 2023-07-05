# Comment réutiliser les éléments avec l'attribut key ?

Relue ?: No

Vue essaie toujours de rendre les éléments aussi efficaces que possible.  Il essaie donc de réutiliser les éléments au lieu de les construire à partir de zéro.  
Mais ce comportement peut causer des problèmes dans quelques scénarios.

Par exemple, si vous essayez de rendre le même élément d'entrée dans les deux `v-if`et `v-else`bloque alors il contient la valeur précédente comme ci-dessous,

```jsx
<template v-if="loginType === 'Admin'">
  <label>Admin</label>
  <input placeholder="Enter your ID">
</template>
<template v-else>
  <label>Guest</label>
  <input placeholder="Enter your name">
</template>
```

Dans ce cas, il ne doit pas être réutilisé. Nous pouvons séparer les deux éléments d'entrée en appliquant  **l'attribut clé**  comme ci-dessous,

```jsx
    <template v-if="loginType === 'Admin'">
      <label>Admin</label>
      <input placeholder="Enter your ID" key="admin-id">
    </template>
    <template v-else>
      <label>Guest</label>
      <input placeholder="Enter your name" key="user-name">
    </template>
```

Le code ci-dessus garantit que les deux entrées sont indépendantes et n'ont pas d'impact l'une sur l'autre.