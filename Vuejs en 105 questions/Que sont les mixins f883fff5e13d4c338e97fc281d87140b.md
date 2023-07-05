# Que sont les mixins ?

Relue ?: No

Mixin nous permet de distribuer des fonctionnalités réutilisables dans les composants Vue.
  Ces fonctions réutilisables sont fusionnées avec des fonctions 
existantes.  Un objet mixin peut contenir n'importe quelle option de 
composant.  Prenons un exemple de mixin avec `created`cycle de vie qui peut être partagé entre les composants,

```jsx
const myMixin = {
  created(){
    console.log("Welcome to Mixins!")
  }
}
var app = new Vue({
  el: '#root',
  mixins: [myMixin]
})
```

> **Remarque :**  plusieurs mixins peuvent être spécifiés dans le tableau mixin du composant.
>