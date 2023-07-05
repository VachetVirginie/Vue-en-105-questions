# Que sont les composants et donnez un exemple ?

Relue ?: No

Les composants sont
 des instances Vue réutilisables avec un nom.  Ils acceptent les mêmes 
options que le nouveau Vue, telles que les données, le calcul, la 
surveillance, les méthodes et les crochets de cycle de vie (à 
l'exception de quelques options spécifiques à la racine comme el).

Prenons un exemple de composant compteur,

```jsx
// Define a new component called button-counter
Vue.component('button-counter', {
  template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
  data: function () {
    return {
      count: 0
    }
  },
})
```

Utilisons ce composant dans une instance racine de Vue créée avec le nouveau Vue

```jsx
<div id="app">
  <button-counter></button-counter>
</div>

var vm = new Vue({ el: '#app' });
```