# Quels sont les modificateurs pris en charge sur le modèle ?

Relue ?: No

Trois modificateurs sont pris en charge pour la directive v-model.

**1. lazy :** 
 par défaut, v-model synchronise l'entrée avec les données après chaque 
événement d'entrée.   Vous pouvez ajouter le modificateur paresseux pour
 synchroniser à la place après les événements de changement.

```jsx
<!-- synced after "change" instead of "input" -->
<input v-model.lazy="msg" >
```

**2. number :** 
 Si vous souhaitez que l'entrée utilisateur soit automatiquement 
convertie en nombre, vous pouvez ajouter le modificateur de nombre à 
votre modèle en V.   Même avec type="number", la valeur des éléments 
d'entrée HTML renvoie toujours une chaîne.   Donc, ce modificateur de 
transtypage est requis.

```jsx
<input v-model.number="age" type="number">
```

**3. trim :** 
 Si vous souhaitez que les espaces blancs de l'entrée utilisateur soient
 automatiquement coupés, vous pouvez ajouter le modificateur trim à 
votre v-model.

```jsx
<input v-model.trim="msg">
```