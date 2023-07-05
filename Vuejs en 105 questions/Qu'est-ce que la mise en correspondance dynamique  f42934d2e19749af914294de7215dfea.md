# Qu'est-ce que la mise en correspondance dynamique des routes ?

Relue ?: No

Parfois, il peut être nécessaire de mapper des itinéraires vers le même composant en fonction d'un modèle.

Prenons un composant utilisateur avec les URL mappées comme `/user/john/post/123`et `/user/jack/post/235`en utilisant des segments dynamiques,

```jsx
const User = {
  template: '<div>User {{ $route.params.name }}, PostId: {{ route.params.postid }}</div>'
}

const router = new VueRouter({
  routes: [
    // dynamic segments start with a colon
    { path: '/user/:name/post/:postid', component: User }
  ]
})
```