# Quelle est la différence entre l'enregistrement local et global dans le système de module ?

Relue ?: No

Dans  **l'enregistrement local**, vous devez créer chaque composant dans le dossier des composants 
(facultatif mais recommandé) et les importer dans une autre section des 
composants du fichier de composants.

Supposons que vous souhaitiez enregistrer les composants A et B dans le composant C, la configuration semble être la suivante,

```jsx
import ComponentA from './ComponentA'
import ComponentB from './ComponentB'

export default {
  components: {
    ComponentA,
    ComponentB
  },
  // ...
}
```

Désormais, ComponentA et ComponentB peuvent être utilisés dans le modèle de ComponentC.

Dans  **l'enregistrement global** , vous devez exporter tous les composants communs ou de base dans un fichier séparé.   Mais certains des bundlers populaires comme `webpack`simplifier ce processus en utilisant `require.context`pour enregistrer globalement les composants de base dans le fichier d'entrée ci-dessous (une seule fois).

```jsx
import Vue from 'vue'
import upperFirst from 'lodash/upperFirst'
import camelCase from 'lodash/camelCase'

const requireComponent = require.context(
  // The relative path of the components folder
  './components',
  // Whether or not to look in subfolders
  false,
  // The regular expression used to match base component filenames
  /Base[A-Z]\w+\.(vue|js)$/)

requireComponent.keys().forEach(fileName => {
  // Get component config
  const componentConfig = requireComponent(fileName)

  // Get PascalCase name of component
  const componentName = upperFirst(
    camelCase(
      // Strip the leading `./` and extension from the filename
      fileName.replace(/^\.\/(.*)\.\w+$/, '$1')
    )
  )

  // Register component globally
  Vue.component(
    componentName,
    // Look for the component options on `.default`, which will
    // exist if the component was exported with `export default`,
    // otherwise fall back to module's root.
    componentConfig.default || componentConfig
  )
})
```