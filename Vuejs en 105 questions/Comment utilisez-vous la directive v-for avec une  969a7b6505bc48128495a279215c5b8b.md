# Comment utilisez-vous la directive v-for avec une plage?

Relue ?: No

Vous pouvez également utiliser le type entier (disons 'n') pour `v-for`directive qui répète l'élément plusieurs fois.

```jsx
<div>
  <span v-for="n in 20">{{ n }} </span>
</div>
```

Il affiche le nombre de 1 à 20.