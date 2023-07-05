# Que sont les modèles en ligne ?

Relue ?: No

Si vous gardez un `inline-template`sur
 un composant enfant, il utilisera son contenu interne comme modèle au 
lieu de le traiter comme un contenu indépendant réutilisable.

```jsx
<my-component inline-template>
   <div>
       <h1>Inline templates</h1>
       <p>Treated as component component owne content</p>
   </div>
</my-component>
```

**Remarque :** 
 même si ces modèles en ligne offrent plus de flexibilité pour la 
création de modèles, il est recommandé de définir le modèle à l'aide de 
la propriété de modèle ou de la balise dans le composant .vue.