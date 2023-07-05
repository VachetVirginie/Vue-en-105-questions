# Comment utilisez-vous les différents CDN ?

Relue ?: No

VueJS est 
disponible dans les CDN jsdelivr, unpkg et cdnjs etc.  Normalement, vous
 pouvez les utiliser à des fins de prototypage ou d'apprentissage.

Par exemple, vous pouvez les utiliser en utilisant jsdelivr avec les dernières versions comme ci-dessous,

```jsx
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.7/dist/vue.js"></script>
```

Vous pouvez l'utiliser pour les modules ES natifs comme ci-dessous,

```jsx
<script type="module">
  import Vue from 'https://cdn.jsdelivr.net/npm/vue@2.6.7/dist/vue.esm.browser.js'
</script>
```

> **Remarque :**  Vous pouvez supprimer le numéro de version pour obtenir la dernière version.
>