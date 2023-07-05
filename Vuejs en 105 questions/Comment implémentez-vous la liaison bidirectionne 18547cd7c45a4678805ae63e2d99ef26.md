# Comment implémentez-vous la liaison bidirectionnelle ?

Relue ?: No

Vous pouvez utiliser le `v-model`directive
 pour créer des liaisons de données bidirectionnelles sur les éléments 
d'entrée de formulaire, de zone de texte et de sélection.

Prenons un exemple en utilisant un composant d'entrée,

```jsx
<input v-model="message" placeholder="Enter input here">
<p>The message is: {{ message }}</p>
```

N'oubliez pas que v-model ignorera l'initiale `value`, `checked`ou `selected`attributs
 trouvés sur tous les éléments de formulaire.  Il utilise donc toujours 
les données d'instance de Vue comme source de vérité.