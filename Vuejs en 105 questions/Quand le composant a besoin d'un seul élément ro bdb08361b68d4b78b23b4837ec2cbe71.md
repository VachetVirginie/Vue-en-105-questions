# Quand le composant a besoin d'un seul élément root ?

Relue ?: No

Dans VueJS 2.x,

 chaque composant doit avoir un seul élément racine  **lorsque le modèle a plus d'un élément**  .   Dans ce cas, vous devez envelopper les éléments avec un élément parent.

```jsx
<template>
   <div class="todo-item">
       <h2>{{ title }}</h2>
       <div v-html="content"></div>
   </div>
</template>
```

Sinon, une erreur se produira, disant que "Le modèle de composant doit contenir exactement un élément racine...".

Alors que dans 3.x,
 les composants peuvent désormais avoir plusieurs nœuds racine.  Cette 
façon d'ajouter plusieurs nœuds racine est appelée fragments.

```jsx
<template>
     <h2>{{ title }}</h2>
     <div v-html="content"></div>
</template>
```