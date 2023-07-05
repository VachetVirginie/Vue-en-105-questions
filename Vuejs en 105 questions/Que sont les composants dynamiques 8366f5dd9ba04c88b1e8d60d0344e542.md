# Que sont les composants dynamiques ?

Relue ?: No

Le composant 
dynamique vous permettra de basculer dynamiquement entre plusieurs 
composants sans mettre à jour la route de l'application et même en 
conservant l'état du composant lors du retour au composant initial.  
Cela fonctionne en utilisant `<component>`tag avec `v-bind:is`attribut qui accepte le composant dynamique.

Créons une instance de vue de composant dynamique pour basculer entre les différentes pages d'un site Web,

```jsx
new Vue({
  el: '#app',
  data: {
    currentPage: 'home'
  },
  components: {
    home: {
      template: "<p>Home</p>"
    },
    about: {
      template: "<p>About</p>"
    },
    contact: {
      template: "<p>Contact</p>"
    }
  }
})
```

Vous pouvez maintenant utiliser le composant dynamique qui contient la page en cours,

```jsx
<div id="app">
   <component v-bind:is="currentPage">
       <!-- component changes when currentPage changes! -->
       <!-- output: Home -->
   </component>
</div>
```

Le composant sera démonté lorsqu'il sera éteint mais il est possible de forcer le composant inactif à fonctionner en utilisant `<keep-alive>`composant

**Remarque :**  La valeur de `:is`L'attribut peut être soit le nom du composant enregistré, soit l'objet importé lui-même.