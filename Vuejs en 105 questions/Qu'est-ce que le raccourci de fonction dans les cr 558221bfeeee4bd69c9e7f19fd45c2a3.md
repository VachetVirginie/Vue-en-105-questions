# Qu'est-ce que le raccourci de fonction dans les crochets directifs ?

Relue ?: No

Dans quelques cas, vous voudrez peut-être le même comportement sur `bind`et `update`crochets indépendamment des autres crochets.  Dans cette situation, vous pouvez utiliser le raccourci de fonction,

```jsx
Vue.directive('theme-switcher', function (el, binding) {
  el.style.backgroundColor = binding.value
})
```