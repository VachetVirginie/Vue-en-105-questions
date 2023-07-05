# Comment configurez-vous vuejs dans webpack?

Relue ?: No

Vous pouvez configurer vueJS dans webpack en utilisant un alias comme ci-dessous,

```jsx
module.exports = {
  // ...
  resolve: {
    alias: {
      'vue$': 'vue/dist/vue.esm.js' // 'vue/dist/vue.common.js' for webpack 1
    }
  }
}
```