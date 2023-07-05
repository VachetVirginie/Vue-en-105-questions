# Que sont les props?

Relue ?: No

Les props sont des attributs personnalisés que vous pouvez enregistrer sur un 
composant.  Lorsqu'une valeur est transmise à un attribut prop, elle 
devient une propriété sur cette instance de composant.  Vous pouvez 
transmettre ces listes de valeurs en tant qu'option d'accessoires et les
 utiliser comme similaires aux variables de données dans le modèle.

```jsx
Vue.component('todo-item', {
  props: ['title'],
  template: '<h2>{{ title }}</h2>'
})
```

Une fois les props enregistrés, vous pouvez les transmettre en tant qu'attributs personnalisés.

```jsx
<todo-item title="Learn Vue conceptsnfirst"></todo-item>
```