# Que sont les modèles X ?

Relue ?: No

Outre les modèles réguliers et les modèles en ligne, vous pouvez également définir des modèles à l'aide d'un élément de script avec le type `text/x-template`puis en référençant le modèle par un identifiant.

Créons un x-template pour un cas d'utilisation simple comme ci-dessous,

```jsx
<script type="text/x-template" id="script-template">
  <p>Welcome to X-Template feature</p>
</script>
```

Vous pouvez maintenant définir le modèle à l'aide de l'ID de référence,

```jsx
Vue.component('x-template-example', {
  template: '#script-template'
})
```