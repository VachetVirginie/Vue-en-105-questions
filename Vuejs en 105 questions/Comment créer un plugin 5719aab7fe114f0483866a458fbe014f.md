# Comment créer un plugin ?

Relue ?: No

Le plugin est créé en exposant un `install`méthode
 qui prend le constructeur Vue comme premier argument avec des options. 
 La structure du plugin VueJS avec des fonctionnalités possibles serait 
la suivante,

```jsx
MyPlugin.install = function (Vue, options) {
  // 1. add global method or property
  Vue.myGlobalMethod = function () {
    // some logic ...
  }

  // 2. add a global asset
  Vue.directive('my-directive', {
    bind (el, binding, vnode, oldVnode) {
      // some logic ...
    }
    // ...
  })

  // 3. inject some component options
  Vue.mixin({
    created: function () {
      // some logic ...
    }
    // ...
  })

  // 4. add an instance method
  Vue.prototype.$myMethod = function (methodOptions) {
    // some logic ...
  }
}
```