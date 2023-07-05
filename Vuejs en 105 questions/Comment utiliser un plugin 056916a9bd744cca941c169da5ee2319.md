# Comment utiliser un plugin ?

Relue ?: No

**Vous pouvez utiliser le plugin en passant votre plugin à la méthode globale use**  .   Vous devez appliquer cette méthode avant de démarrer votre application en appelant new Vue().

```jsx
// calls `MyPlugin.install(Vue, { someOption: true })`
Vue.use(MyPlugin)

new Vue({
  //... options
})
```