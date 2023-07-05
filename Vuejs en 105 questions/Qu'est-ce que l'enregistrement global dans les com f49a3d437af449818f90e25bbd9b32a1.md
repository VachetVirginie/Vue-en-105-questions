# Qu'est-ce que l'enregistrement global dans les composants ?

Relue ?: No

Les composants qui sont globalement enregistrés peuvent être utilisés dans le modèle de n'importe quelle instance racine de Vue (nouvelle Vue) créée après 
l'enregistrement.

Dans l'enregistrement global, les composants créés à l'aide de Vue.component comme ci-dessous,

```jsx
Vue.component('my-component-name', {
  // ... options ...
})
```

Prenons plusieurs composants qui sont globalement enregistrés dans l'instance vue,

```jsx
Vue.component('component-a', { /* ... */ })
Vue.component('component-b', { /* ... */ })
Vue.component('component-c', { /* ... */ })

new Vue({ el: '#app' })
```

Les composants ci-dessus peuvent être utilisés dans l'instance vue,

```jsx
<div id="app">
  <component-a></component-a>
  <component-b></component-b>
  <component-c></component-c>
</div>
```

N'oubliez pas que les composants peuvent également être utilisés dans des sous-composants.