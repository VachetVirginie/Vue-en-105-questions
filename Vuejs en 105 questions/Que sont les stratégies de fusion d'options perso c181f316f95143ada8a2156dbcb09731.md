# Que sont les stratégies de fusion d'options personnalisées ?

Relue ?: No

Vue utilise la stratégie par défaut qui écrase la valeur existante tandis que les 
options personnalisées sont fusionnées.  Mais si vous souhaitez 
fusionner une option personnalisée à l'aide d'une connexion 
personnalisée, vous devez attacher une fonction à `Vue.config.optionMergeStrategies`

Pour l'exemple, la structure de `myOptions`l'option personnalisée serait comme ci-dessous,

```jsx
Vue.config.optionMergeStrategies.myOption = function (toVal, fromVal) {
  // return mergedVal
}
```

Prenons ci-dessous la stratégie de fusion Vuex 1.0 comme exemple avancé,

```jsx
const merge = Vue.config.optionMergeStrategies.computed
Vue.config.optionMergeStrategies.vuex = function (toVal, fromVal) {
  if (!toVal) return fromVal
  if (!fromVal) return toVal
  return {
    getters: merge(toVal.getters, fromVal.getters),
    state: merge(toVal.state, fromVal.state),
    actions: merge(toVal.actions, fromVal.actions)
  }
}
```