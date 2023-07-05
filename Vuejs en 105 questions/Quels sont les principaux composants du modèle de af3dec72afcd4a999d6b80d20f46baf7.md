# Quels sont les principaux composants du modèle de gestion d'état ?

Relue ?: No

La gestion d'état al'état, la vue et les actions comme composants principaux.  Le modèle suivi par ces composants dans une application est appelé modèle de 
gestion d'état.  Ci-dessous les composants en détail:

1. L'  **état**
    
    , qui est la source de vérité qui anime notre application
    
2. La  **vue**
    
    , qui n'est qu'un mappage déclaratif de l'état
    
3. Les  **actions**
    
    , qui sont les manières possibles dont l'état peut changer en réaction aux entrées de l'utilisateur à partir de la vue.
    

Prenons un contre-exemple qui suit le modèle de gestion d'état avec les 3 composants ci-dessus,

```jsx
 new Vue({
   // state
   data () {
     return {
       count: 0
     }
   },
   // view
   template: `
     <div>{{ count }}</div>
   `,
   // actions
   methods: {
     increment () {
       this.count++
     }
   }
 })
```