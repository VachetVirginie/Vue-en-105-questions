# Quelles sont les différentes manières de créer des filtres ?

Relue ?: No

Vous pouvez définir des filtres de deux manières,

1. **Filtres locaux :**
    
    Vous pouvez définir des filtres locaux dans les options d'un 
    composant.   Dans ce cas, le filtre s'applique à ce composant 
    spécifique.
    

```jsx
filters: {
  capitalize: function (value) {
    if (!value) return ''
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1)
  }
}
```

1. **Filtres globaux :**
    
    Vous pouvez également définir un filtre globalement avant de créer 
    l'instance de Vue.   Dans ce cas, le filtre est applicable à tous les 
    composants avec dans l'instance de vue,
    

```jsx
Vue.filter('capitalize', function (value) {
  if (!value) return ''
  value = value.toString()
  return value.charAt(0).toUpperCase() + value.slice(1)
})

new Vue({
  // ...
})
```