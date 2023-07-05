# Quels sont les types de props possibles ?

Relue ?: No

Vous pouvez déclarer des accessoires avec ou sans type.  Mais il est recommandé 
d'avoir des types d'accessoires car ils fournissent la documentation du 
composant et avertissent le développeur de tout type de données 
incorrect attribué.

```jsx
props: {
  name: String,
  age: Number,
  isAuthenticated: Boolean,
  phoneNumbers: Array,
  address: Object
}
```

Comme mentionné dans l'extrait de code ci-dessus, vous pouvez répertorier les 
accessoires en tant qu'objet, où les noms et les valeurs des propriétés 
contiennent respectivement les noms et les types d'accessoires.