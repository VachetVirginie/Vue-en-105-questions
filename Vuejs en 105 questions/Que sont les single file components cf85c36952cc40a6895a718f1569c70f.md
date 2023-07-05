# Que sont les single file components?

Relue ?: No

Les composants de fichier unique sont un concept facile à comprendre.  

Plus tôt, vous avez peut-être entendu parler des trois parties (HTML, JavaScript et CSS) de votre application conservées dans différents composants.  Mais les 
composants de fichier unique encapsulent la structure, le style et le 
comportement dans un seul fichier.  Au début, il semble étrange d'avoir 
les trois parties dans un seul fichier, mais cela a en fait beaucoup 
plus de sens.

Prenons un exemple de composants de fichier unique

```jsx
<template>
  <div>
    <h1>Welcome {{ name }}!</h1>
  </div>
</template>

<script>
module.exports = {
  data: function() {
    return {
      name: 'John'    }
  }
}
</script>

<style scoped>
h1 {
  color: #34c779;
  padding: 3px;
}
</style>
```