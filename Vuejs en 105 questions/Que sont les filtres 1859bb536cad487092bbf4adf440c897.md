# Que sont les filtres ?

Relue ?: No

Les filtres peuvent être utilisés pour appliquer une mise en forme de texte courante.  Ces filtres doivent être ajoutés à la fin de l'expression JavaScript, 
indiqués par le symbole "tuyau".  Vous pouvez les utiliser dans deux cas
 précis :

1. interpolations de moustache
2. expressions v-bind

Par exemple, définissons un filtre local nommé capitaliser dans les options d'un composant

```jsx
filters: {
  capitalize: function (value) {
    if (!value) return ''
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1)
  }
}
```

Vous pouvez maintenant utiliser le filtre dans l'interpolation de la moustache ou dans l'expression v-bind,

```jsx
<!-- in mustaches -->
{{ username | capitalize }}

<!-- in v-bind -->
<div v-bind:id="username | capitalize"></div>
```