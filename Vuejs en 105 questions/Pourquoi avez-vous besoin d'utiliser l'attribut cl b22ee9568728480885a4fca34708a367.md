# Pourquoi avez-vous besoin d'utiliser l'attribut clé pour la directive ?

Relue ?: No

Afin de suivre l'identité de chaque nœud, et donc de réutiliser et de réorganiser les éléments existants, vous devez fournir un `key`attribut pour chaque élément avec dans `v-for`itération.  Une valeur idéale pour la clé serait l'identifiant unique de chaque élément.

Prenons un exemple d'utilisation,

```jsx
<div v-for="item in items" :key="item.id">
  {{item.name}}
</div>
```

Par conséquent, il est toujours recommandé de fournir une clé avec v-for dans la mesure du possible, à moins que le contenu DOM itéré soit simple.

> **Remarque :** 
 Vous ne devez pas utiliser de valeurs non primitives telles que des 
objets et des tableaux en tant que clés v-for.   Utilisez plutôt des 
chaînes ou des valeurs numériques.
>