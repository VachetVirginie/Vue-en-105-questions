# Quels sont les modificateurs de bouton de souris pris en charge ?

Relue ?: No

Vue prend en charge les modificateurs de bouton de souris ci-dessous

1. .left
2. .right
3. .middle

Par exemple, l'utilisation de `.right`modificateur comme ci-dessous

```jsx
 <button
   v-if="button === 'right'"v-on:mousedown.right="increment"v-on:mousedown.left="decrement"
 />
```