# Comment pouvez-vous écrire des nœuds virtuels en double dans un composant ?

Relue ?: No

Tous les nœuds virtuels (VNodes) de l'arborescence des composants doivent être uniques, c'est-à-dire que vous ne pouvez pas écrire des nœuds dupliqués de 
manière simple.  Si vous souhaitez dupliquer plusieurs fois le même 
élément/composant, vous devez utiliser la fonction d'usine.

La fonction de rendu ci-dessous n'est pas valide lorsque vous essayez de dupliquer l'élément h1 3 fois,

```jsx
render: function (createElement) {
  var myHeadingVNode = createElement('h1', 'This is a Virtual Node')
  return createElement('div', [
    myHeadingVNode, myHeadingVNode, myHeadingVNode
  ])
}
```

Vous pouvez faire des doublons avec la fonction d'usine,

```jsx
render: function (createElement) {
  return createElement('div',
    Array.apply(null, { length: 3 }).map(function () {
      return createElement('h1', 'This is a Virtual Node')
    })
  )
}
```