# Quelles sont les mises en garde de la détection des changements d'objet ?

Relue ?: No

Vue ne peut pas détecter les modifications apportées à l'objet lors de l'ajout ou de la suppression de propriétés.

Prenons un exemple de modifications de données utilisateur,

```jsx
var vm = new Vue({
  data: {
    user: {
      name: 'John'
    }
  }
})

// `vm.name` is now reactive

vm.user.email = john@email.com // `vm.user.email` is NOT reactive
```

Vous pouvez surmonter ce scénario en utilisant la méthode Vue.set(object, key, value) ou Object.assign(),

```jsx
Vue.set(vm.user, 'email', 'john@email.com');
// (or)
vm.user = Object.assign({}, vm.user, {
  email: john@email.com
})
```