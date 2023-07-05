# Que sont les mixins globaux ?

Relue ?: No

Parfois, il est 
nécessaire d'étendre les fonctionnalités de Vue ou d'appliquer une 
option à tous les composants Vue disponibles dans notre application.  
Dans ce cas, les mixins peuvent être appliqués globalement pour affecter
 tous les composants de Vue.  Ces mixins sont appelés mixins globaux.

Prenons un exemple de mixin global,

```jsx
Vue.mixin({
  created(){
    console.log("Write global mixins")
  }
})

new Vue({
  el: '#app'
})
```

Dans le mixin global ci-dessus, les options de mixin se répartissent sur tous les 
composants avec la console en cours d'exécution lors de la création de 
l'instance.  Celles-ci sont utiles lors des tests, du débogage ou des 
bibliothèques tierces.  Dans le même temps, vous devez utiliser ces 
mixins globaux de manière parcimonieuse et prudente, car cela affecte 
chaque instance de Vue créée, y compris les composants tiers.