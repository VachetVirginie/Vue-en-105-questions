# Quelles sont les directives conditionnelles ?

Relue ?: No

VueJS fournit un ensemble de directives pour afficher ou masquer des éléments en fonction
 de conditions.   Les directives disponibles sont :  **v-if, v-else, v-else-if et v-show**

**1. v-if :** 
 La directive v-if ajoute ou supprime des éléments DOM en fonction de 
l'expression donnée.   Par exemple, le bouton ci-dessous ne s'affichera 
pas si isLoggedIn est défini sur false.

```jsx
<button v-if="isLoggedIn">Logout</button>
```

Vous pouvez également contrôler plusieurs éléments avec une seule instruction v-if en enveloppant tous les éléments dans un `<template>`élément avec la condition.  Par exemple, vous pouvez avoir à la fois l'étiquette et le bouton appliqués sous condition,

```jsx
<template v-if="isLoggedIn">
  <label> Logout </button>
  <button> Logout </button>
</template>
```

**2. v-else :** 
 cette directive est utilisée pour afficher le contenu uniquement 
lorsque l'expression adjacente à v-if se résout à faux.   Ceci est 
similaire au bloc else dans n'importe quel langage de programmation pour
 afficher un contenu alternatif et il est précédé du bloc v-if ou 
v-else-if .   Vous n'avez pas besoin de transmettre de valeur à this. 
  Par exemple, v-else est utilisé pour afficher le bouton Connexion si 
isLoggedIn est défini sur false (non connecté).

```jsx
<button v-if="isLoggedIn"> Logout </button>
<button v-else> Log In </button>
```

**3. v-else-if :** 
 Cette directive est utilisée lorsque nous avons besoin de plus de deux 
options à vérifier. 
  Par exemple, nous voulons afficher du texte au lieu du bouton LogIn 
lorsque la propriété ifLoginDisabled est définie sur true.   Ceci peut 
être réalisé par l'instruction v-else.

```jsx
<button v-if="isLoggedIn"> Logout </button>
<label v-else-if="isLoginDisabled"> User login disabled </label>
<button v-else> Log In </button>
```

**4. v-show :** 
 Cette directive est similaire à v-if mais elle affiche tous les 
éléments dans le DOM et utilise ensuite la propriété CSS display pour 
afficher/masquer les éléments.   Cette directive est recommandée si les 
éléments sont allumés et éteints fréquemment.

```jsx
<span v-show="user.name">Welcome user,{{user.name}}</span>
```