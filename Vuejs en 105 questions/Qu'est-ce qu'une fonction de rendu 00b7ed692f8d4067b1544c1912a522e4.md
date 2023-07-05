# Qu'est-ce qu'une fonction de rendu ?

Relue ?: No

La fonction de rendu est une fonction normale qui reçoit un `createElement`comme
 premier argument utilisé pour créer des nœuds virtuels.  En interne, 
les modèles de Vue.js se compilent pour rendre les fonctions au moment 
de la construction.  Par conséquent, les modèles ne sont que du sucre 
syntaxique des fonctions de rendu.

Prenons un exemple de balisage Div simple et de la fonction de rendu correspondante.
 Le balisage HTML peut être écrit dans la balise de modèle comme ci-dessous,

```jsx
<template>
  <div :class="{'is-rounded': isRounded}">
    <p>Welcome to Vue render functions</p>
  </div>
</template>
```

et la fonction de rendu compilée ou explicite apparaîtrait comme ci-dessous,

```jsx
render: function (createElement) {
  return createElement('div', {
    'class': {
      'is-rounded': this.isRounded
     }
  }, [
    createElement('p', 'Welcome to Vue render functions')
  ]);
}
```

> **Remarque :**  Les composants de réaction sont construits avec des fonctions de rendu dans JSX.
>