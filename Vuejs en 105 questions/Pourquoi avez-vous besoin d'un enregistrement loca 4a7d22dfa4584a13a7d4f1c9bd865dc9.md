# Pourquoi avez-vous besoin d'un enregistrement local ?

Relue ?: No

En raison de l'enregistrement global, même si vous n'utilisez pas le composant, il 
peut toujours être inclus dans votre version finale.  Cela créera donc 
du javascript inutile dans l'application.  Cela peut être évité en 
utilisant l'enregistrement local avec les étapes ci-dessous,

1. Vous devez d'abord définir vos composants en tant qu'objets JavaScript simples
    
    ```jsx
    var ComponentA = { /* ... */ }
    var ComponentB = { /* ... */ }
    var ComponentC = { /* ... */ }
    ```
    
    Les composants enregistrés localement ne seront pas disponibles dans les 
    sous-composants.  Dans ce cas, vous devez les ajouter dans la section 
    des composants
    
    ```jsx
    var ComponentA = { /* ... */ }
    
    var ComponentB = {
      components: {
        'component-a': ComponentA
      },
      // ...
    }
    ```
    
2. Vous pouvez utiliser les composants dans la section composants de l'instance vue,
    
    ```jsx
    new Vue({
      el: '#app',
      components: {
        'component-a': ComponentA,
        'component-b': ComponentB
      }
    })
    ```