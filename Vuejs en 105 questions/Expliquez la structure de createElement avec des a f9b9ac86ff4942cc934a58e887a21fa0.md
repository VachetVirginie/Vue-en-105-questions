# Expliquez la structure de createElement avec des arguments ?

Relue ?: No

Le createElement accepte peu d'arguments pour utiliser toutes les fonctionnalités du modèle.

Voyons la structure de base de createElement avec les arguments possibles,

```jsx
// @returns {VNode}
createElement(
  // An HTML tag name, component options, or async function resolving to one of these.
  // Type is {String | Object | Function}
  // Required.
  'div',

  // A data object corresponding to the attributes you would use in a template.
  // Type is {Object}
  // Optional.
  {
    // Normal HTML attributes
    attrs: {
      id: 'someId'
    },
    // Component props
    props: {
      myProp: 'somePropValue'
    },
    // DOM properties
    domProps: {
      innerHTML: 'This is some text'
    },
    // Event handlers are nested under `on`
    on: {
      click: this.clickHandler
    },
    // Similar to `v-bind:style`, accepting either a string, object, or array of objects.
    style: {
      color: 'red',
      fontSize: '14px'
    },
    // Similar to `v-bind:class`, accepting either a string, object, or array of strings and objects.
    class: {
      classsName1: true,
      classsName2: false
    }
    // ....
  },

  // Children VNodes, built using `createElement()`, or using strings to get 'text VNodes'.
  // Type is {String | Array}
  // Optional.
  [
    'Learn about createElement arguments.',
    createElement('h1', 'Headline as a child virtual node'),
    createElement(MyComponent, {
      props: {
        someProp: 'This is a prop value'
      }
    })
  ]
)
```

Voir les détails de l'objet date dans  [la doc](https://vuejs.org/v2/guide/render-function.html#The-Data-Object-In-Depth)  officielle .