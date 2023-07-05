# Comment rendre les modifications des paramètres du routeur réactives ?

Relue ?: No

Lorsque vous 
naviguez d'une URL à une autre (mappée avec un seul composant) en 
utilisant des routes avec des paramètres, la même instance de composant 
sera réutilisée.  Même si c'est plus efficace que de détruire l'ancienne
 instance puis d'en créer une nouvelle, les hooks de cycle de vie du 
composant ne seront pas appelés.

Ce problème peut être résolu en utilisant l'une des approches ci-dessous,

1. **Regardez l'objet $route :**
    
    ```jsx
    const User = {
      template: '<div>User {{ $route.params.name }} </div>',
      watch: {
        '$route' (to, from) {
          // react to route changes...
        }
      }
    }
    ```
    
2. **Utiliser le garde de navigation beforeRouteUpdate :**
    
    Ceci n'est disponible que depuis la version 2.2.
    
    ```jsx
    const User = {
      template: '<div>User {{ $route.params.name }} </div>',
      beforeRouteUpdate (to, from, next) {
        // react to route changes and then call next()
      }
    }
    ```
    

Notez que le garde beforeRouteEnter n'a PAS accès à `this`.  Au lieu de cela, vous pouvez passer un rappel à `next`pour accéder à l'instance de vm.