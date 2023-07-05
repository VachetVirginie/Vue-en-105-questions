# Comment définissez-vous les alias de modificateurs de clé personnalisés ?

Relue ?: No

Vous pouvez définir des alias de modificateur de clé personnalisés via le global `config.keyCodes`. 

 Il y a peu de lignes directrices pour les propriétés

1. Vous ne pouvez pas utiliser camelCase. Au lieu de cela, vous pouvez utiliser kebab-case avec des guillemets doubles
2. Vous pouvez définir plusieurs valeurs dans un format de tableau

```jsx
Vue.config.keyCodes = {
  f1: 112,
  "media-play-pause": 179,
  down: [40, 87]
}
```