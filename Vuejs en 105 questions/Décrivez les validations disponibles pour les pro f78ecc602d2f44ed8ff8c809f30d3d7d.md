# Décrivez les validations disponibles pour les props ?

Relue ?: No

Vue fournit des validations telles que les types, les champs obligatoires, les valeurs 
par défaut ainsi que des validations personnalisées.  Vous pouvez 
fournir un objet avec des exigences de validation à la valeur des 
accessoires comme ci-dessous,

Prenons un exemple de composant de profil utilisateur Vue avec des validations possibles,

```jsx
Vue.component('user-profile', {
  props: {
    // Basic type check (`null` matches any type)
    age: Number,
    // Multiple possible types
    identityNumber: [String, Number],
    // Required string
    email: {
      type: String,
      required: true
    },
    // Number with a default value
    minBalance: {
      type: Number,
      default: 10000
    },
    // Object with a default value
    message: {
      type: Object,
      // Object or array defaults must be returned from
      // a factory function
      default: function () {
        return { message: 'Welcome to Vue' }
      }
    },
    // Custom validator function
    location: {
      validator: function (value) {
        // The value must match one of these strings
        return ['India', 'Singapore', 'Australia'].indexOf(value) !== -1
      }
    }
  }
})
```