# Quelles sont les étapes pour utiliser vue router et donner un exemple ?

Relue ?: No

Il est facile d'intégrer vue router dans l'application vue.

Voyons l'exemple avec des instructions étape par étape.

**Étape 1 :**  Configurer le lien du routeur et la vue du routeur dans le modèle

```jsx
<script src="https://unpkg.com/vue/dist/vue.js"></script>
<script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

<div id="app">
  <h1>Welcome to Vue routing app!</h1>
  <p>
    <!-- use router-link component for navigation using `to` prop. It rendered as an `<a>` tag -->
    <router-link to="/home">Home</router-link>
    <router-link to="/services">Services</router-link>
  </p>
  <!-- route outlet in which component matched by the route will render here -->
  <router-view></router-view>
</div>
```

**Étape 2 :**  Importez les packages Vue et VueRouter, puis appliquez le routeur

```jsx
import Vue from 'vue';
import VueRouter from 'vue-router';

Vue.use(VueRouter)
```

**Étape 3 :**  Définissez ou importez des composants de routage.

```jsx
const Home = { template: '<div>Home</div>' }
const Services = { template: '<div>Services</div>' }
```

**Étape 4 :**  Définissez votre itinéraire où chacun correspond à un composant

```jsx
const routes = [
  { path: '/home', component: Home },
  { path: '/services', component: Services }
]
```

**Étape 5 :**  Créez l'instance de routeur et transmettez `routes`option

```jsx
const router = new VueRouter({
  routes // short for `routes: routes`
})
```

**Étape 6 :**  Créez et montez l'instance racine.

```jsx
const app = new Vue({
  router
}).$mount('#app')
```

Vous pouvez maintenant naviguer sur différentes pages (Accueil, Services) avec l'application Vue.