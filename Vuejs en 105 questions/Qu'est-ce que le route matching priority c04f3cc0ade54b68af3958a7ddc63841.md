# Qu'est-ce que le route matching priority?

Relue ?: No

Parfois, l'URL peut
 correspondre à plusieurs routes et la confusion quant à la route à 
mapper est résolue par la priorité de correspondance des routes.  La 
priorité est basée sur l'ordre de configuration des routes.  
c'est-à-dire que la route déclarée en premier a une priorité plus 
élevée.

```jsx
const router = new VueRouter({
       routes: [
         // dynamic segments start with a colon
         { path: '/user/:name', component: User } // This route gets higher priority
         { path: '/user/:name', component: Admin }
         { path: '/user/:name', component: Customer }
       ]
     })
```