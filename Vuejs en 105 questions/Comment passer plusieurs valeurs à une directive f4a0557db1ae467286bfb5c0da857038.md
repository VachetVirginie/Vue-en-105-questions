# Comment passer plusieurs valeurs à une directive ?

Relue ?: No

Une directive peut 
prendre n'importe quelle expression javascript valide.  Donc, si vous 
souhaitez transmettre plusieurs valeurs, vous pouvez transmettre un 
littéral d'objet JavaScript.

Passons l'objet littéral à une directive avatar comme ci-dessous

```jsx
<div v-avatar="{ width: 500, height: 400, url: 'path/logo', text: 'Iron Man' }"></div>
```

Maintenant, configurons globalement la directive avatar,

```jsx
Vue.directive('avatar', function (el, binding) {
  console.log(binding.value.width) // 500
  console.log(binding.value.height)  // 400
  console.log(binding.value.url) // path/logo
  console.log(binding.value.text)  // "Iron Man"
})
```