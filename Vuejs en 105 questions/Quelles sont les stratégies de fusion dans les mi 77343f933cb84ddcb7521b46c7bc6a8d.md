# Quelles sont les stratégies de fusion dans les mixins ?

Relue ?: No

Lorsqu'un mixin et le composant lui-même contiennent des options qui se chevauchent, les options seront fusionnées en fonction de certaines stratégies.

1. Les objets de données
subissent une fusion récursive, les données du composant ayant priorité
sur les mixins en cas de chevauchement ou de conflit.
    
    ```jsx
    var mixin = {
      data: function () {
        return {
          message: 'Hello, this is a Mixin'
        }
      }
    }
    new Vue({
      mixins: [mixin],
      data: function () {
        return {
          message: 'Hello, this is a Component'
        }
      },
      created: function () {
        console.log(this.$data); // => { message: "Hello, this is a Component'" }
      }
    })
    ```
    
2. Les fonctions Hook qui se
chevauchent ont été fusionnées dans un tableau afin que toutes soient
appelées. Les hooks Mixin seront appelés avant les propres hooks du
composant.
    
    ```jsx
    const myMixin = {
      created(){
        console.log("Called from Mixin")
      }
    }
    
    new Vue({
      el: '#root',
      mixins: [myMixin],
      created(){
        console.log("Called from Component")
      }
    })
    
    // Called from Mixin
    // Called from Component
    ```
    
3. Les options qui attendent des valeurs d'objet (comme les méthodes, les composants et les directives)
seront fusionnées dans le même objet. Dans ce cas, les options du
composant seront prioritaires en cas de conflits de clés dans ces
objets.
    
    ```jsx
    var mixin = {
      methods: {
        firstName: function () {
          console.log('John')
        },
        contact: function () {
          console.log('+65 99898987')
        }
      }
    }
    
    var vm = new Vue({
      mixins: [mixin],
      methods: {
        lastName: function () {
          console.log('Murray')
        },
        contact: function () {
          console.log('+91 893839389')
        }
      }
    })
    
    vm.firstName() // "John"
    vm.lastName() // "Murray"
    vm.contact() // "+91 893839389"
    ```