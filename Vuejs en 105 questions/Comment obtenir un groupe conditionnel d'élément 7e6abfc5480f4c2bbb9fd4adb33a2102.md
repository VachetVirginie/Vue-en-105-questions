# Comment obtenir un groupe conditionnel d'éléments ?

Relue ?: No

Vous pouvez obtenir un groupe conditionnel d'éléments (basculer plusieurs éléments à la fois) en appliquant  **la directive v-if**  sur `<template>`élément qui fonctionne comme wrapper invisible (pas de rendu) pour un groupe d'éléments.

Par exemple, vous pouvez grouper conditionnellement les détails de l'utilisateur en 
fonction d'une condition d'utilisateur valide.

```jsx
<template v-if="condition">
  <h1>Name</h1>
  <p>Address</p>
  <p>Contact Details</p>
</template>
```