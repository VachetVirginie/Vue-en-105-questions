# Que sont les nested routes?

Relue ?: No

Généralement, l'application est composée de composants imbriqués qui sont imbriqués à 
plusieurs niveaux.  Les segments d'une URL correspondent à une certaine 
structure de ces composants imbriqués.  Pour rendre les composants dans 
la prise imbriquée, vous devez utiliser le `children`option dans `VueRouter`configuration constructeur.

Prenons une 
application utilisateur composée de profils et de composants imbriqués 
avec des itinéraires respectifs.  Vous pouvez également définir une 
configuration de route par défaut lorsqu'il n'y a pas de route imbriquée
 correspondante.

```jsx
const router = new VueRouter({
  routes: [
    { path: '/user/:id', component: User,
      children: [
        {
          // UserProfile will be rendered inside User's <router-view> when /user/:id/profile is matched
          path: 'profile',
          component: UserProfile
        },
        {
          // UserPosts will be rendered inside User's <router-view> when /user/:id/posts is matched
          path: 'posts',
          component: UserPosts
        },
          // UserHome will be rendered inside User's <router-view> when /user/:id is matched
        {  path: '',
           component: UserHome },
      ]
    }
  ]
})
```