# Quel est le but de renderError ?

Relue ?: No

Lorsque la fonction
 de rendu par défaut rencontre une erreur, vous pouvez utiliser 
rennderError comme sortie de rendu alternative.  L'erreur sera transmise
 à renderError comme deuxième argument.

L'exemple d'utilisation de renderError est comme ci-dessous,

```jsx
new Vue({
  render (h) {
    throw new Error('An error')
  },
  renderError (h, err) {
    return h('div', { style: { color: 'red' }}, err.stack)
  }
}).$mount('#app')
```