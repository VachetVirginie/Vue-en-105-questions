# Quelles sont les méthodes de cycle de vie de VueJS ?

Relue ?: No

Les hooks cycle de vie sont une fenêtre sur la façon dont la bibliothèque que vous
 utilisez fonctionne en arrière-plan.  En utilisant ces hooks, vous 
saurez quand votre composant est créé, ajouté au DOM, mis à jour ou 
détruit.  Regardons le diagramme du cycle de vie avant d'aller en détail
 à chaque crochet du cycle de vie,

![https://github.com/sudheerj/vuejs-interview-questions/raw/master/images/lifecycle.png](https://github.com/sudheerj/vuejs-interview-questions/raw/master/images/lifecycle.png)

1. **Création (Initialisation): Remarque :**
    
    Les crochets de création vous permettent d'effectuer des actions avant
     même que votre composant ait été ajouté au DOM.   Vous devez utiliser 
    ces crochets si vous devez configurer des éléments dans votre composant à
     la fois pendant le rendu client et le rendu serveur.   Contrairement 
    aux autres crochets, les crochets de création sont également exécutés 
    lors du rendu côté serveur.
    
    1. `beforeCreate` : Ce crochet s'exécute à l'initialisation même de votre composant. hook
    observe les données et les événements d'initialisation dans votre
    composant. Ici, les données ne sont toujours pas réactives et les
    événements qui se produisent pendant le cycle de vie du composant n'ont
    pas encore été configurés.
    
    ```jsx
        new Vue({
          data: {
           count: 10
          },
          beforeCreate: function () {
            console.log('Nothing gets called at this moment')
            // `this` points to the view model instance
            console.log('count is ' + this.count);
          }
        })
           // count is undefined
    ```
    
    1. `created`: Ce hook est invoqué lorsque Vue a configuré les événements et
    l'observation des données. Ici, les événements sont actifs et l'accès
    aux données réactives est activé bien que les modèles n'aient pas encore été montés ou rendus.
    
    ```jsx
      new Vue({
        data: {
         count: 10
        },
        created: function () {
          // `this` points to the view model instance
          console.log('count is: ' + this.count)
        }
      })
         // count is: 10
    ```
    
    N'oubliez pas que vous n'aurez pas accès au DOM ou à l'élément de 
    montage cible (this.$el) à l'intérieur des crochets de création
    
2. **Montage (insertion DOM) :**
    
    Les crochets de montage sont souvent les crochets les plus utilisés et
     ils vous permettent d'accéder à votre composant immédiatement avant et 
    après le premier rendu.
    
    1. `beforeMount` : Le beforeMount vous permet d'accéder à votre composant immédiatement avant et après le premier rendu.
    
    ```jsx
      new Vue({
        beforeMount: function () {
          // `this` points to the view model instance
          console.log(`this.$el is yet to be created`);
        }
      })
    ```
    
    1. `mounted`: C'est un crochet le plus utilisé et vous aurez un accès complet au
    composant réactif, aux modèles et au DOM rendu (via. this.$el). Les
    modèles les plus fréquemment utilisés sont la récupération de données
    pour votre composant.
    
    ```jsx
    <div id="app">
        <p>I’m text inside the component.</p>
    </div>
      new Vue({
        el: ‘#app’,
        mounted: function() {
          console.log(this.$el.textContent); // I'm text inside the component.
        }
      })
    ```
    
3. **Mise à jour (Diff & Re-render):**
    
    Les crochets de mise à jour sont appelés chaque fois qu'une propriété 
    réactive utilisée par votre composant change ou que quelque chose 
    d'autre provoque son nouveau rendu.
    
    1. `beforeUpdate`: Le hook beforeUpdate s'exécute après la modification des données sur
    votre composant et le cycle de mise à jour commence, juste avant que le
    DOM ne soit corrigé et rendu à nouveau.
    
    ```jsx
    <div id="app">
      <p>{{counter}}</p>
    </div>
    ...// rest of the code
      new Vue({
        el: '#app',
        data() {
          return {
            counter: 0
          }
        },
         created: function() {
          setInterval(() => {
            this.counter++
          }, 1000)
        },
    
        beforeUpdate: function() {
          console.log(this.counter) // Logs the counter value every second, before the DOM updates.
        }
      })
    ```
    
    1. `updated`: Ce crochet s'exécute après les modifications de données sur votre composant et le nouveau rendu du DOM.
    
    ```jsx
    <div id="app">
      <p ref="dom">{{counter}}</p>
    </div>
    ...//
      new Vue({
        el: '#app',
        data() {
          return {
            counter: 0
          }
        },
         created: function() {
          setInterval(() => {
            this.counter++
          }, 1000)
        },
        updated: function() {
          console.log(+this.$refs['dom'].textContent === this.counter) // Logs true every second
        }
      })
    ```
    
4. **Destruction (démantèlement):**
    
    Les crochets de destruction vous permettent d'effectuer des actions 
    lorsque votre composant est détruit, comme le nettoyage ou l'envoi 
    d'analyses.
    
    1. `beforeDestroy` : `beforeDestroy`
        
        est
         tiré juste avant le démontage.  Si vous avez besoin de nettoyer des 
        événements ou des abonnements réactifs, beforeDestroy serait 
        probablement le moment de le faire.  Votre composant sera toujours 
        entièrement présent et fonctionnel.
        
    
    ```jsx
    new Vue ({
      data() {
        return {
          message: 'Welcome VueJS developers'
        }
      },
    
      beforeDestroy: function() {
        this.message = null
        delete this.message
      }
    })
    ```
    
    1. `destroyed`: Ce crochet est appelé après que votre composant a été détruit, ses
    directives ont été dissociées et ses écouteurs d'événement ont été
    supprimés.
    
    ```jsx
    new Vue ({
        destroyed: function() {
          console.log(this) // Nothing to show here
        }
      })
    ```