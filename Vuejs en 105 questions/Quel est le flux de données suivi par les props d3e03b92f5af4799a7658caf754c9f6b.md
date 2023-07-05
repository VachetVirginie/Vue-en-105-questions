# Quel est le flux de données suivi par les props ?

Relue ?: No

Tous les props suivent une liaison unidirectionnelle entre la propriété 
enfant et la propriété parent.  c'est-à-dire que lorsque la propriété 
parent est mise à jour, cette dernière valeur prop sera transmise à 
l'enfant, mais pas l'inverse (enfant à parent).  Le composant enfant ne 
doit pas muter le prop sinon il lance un avertissement dans la console.
 Les cas de mutation possibles peuvent être résolus comme ci-dessous,

1. Lorsque vous essayez d'utiliser parent prop comme valeur initiale pour la propriété enfant :
    
    Dans ce cas, vous 
    pouvez définir une propriété locale dans le composant enfant et 
    attribuer la valeur parent comme valeur initiale
    
    ```jsx
    props: ['defaultUser'],
    data: function () {
      return {
        username: this.defaultUser
      }
    }
    ```
    
2. Lorsque vous essayez de transformer l'accessoire parent :
    
    Vous pouvez définir une propriété calculée en utilisant la valeur de la prop,
    
    ```jsx
    props: ['environment'],
    computed: {
      localEnvironment: function () {
        return this.environment.trim().toUpperCase()
      }
    }
    ```