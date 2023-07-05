# Qu'est-ce qu'un vuejs loader?

Relue ?: No

Vue loader est un 
chargeur pour webpack qui vous permet de créer des composants Vue dans 
un format appelé composants à fichier unique (SFC).

Par exemple, il crée le composant HelloWorld dans un SFC,

```jsx
<template>
  <div class="greeting">{{ message }}</div>
</template>

<script>
export default {
  data () {
    return {
      message: 'Hello world for vueloader!'
    }
  }
}
</script>

<style>
.greeting {
  color: blue;
}
</style>
```