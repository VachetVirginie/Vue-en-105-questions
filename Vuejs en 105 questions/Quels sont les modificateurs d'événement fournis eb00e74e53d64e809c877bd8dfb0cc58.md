# Quels sont les modificateurs d'événement fournis par vue ?

Relue ?: No

Normalement, javascript fournit `event.preventDefault() or event.stopPropagation()`à
 l'intérieur des gestionnaires d'événements.  Vous pouvez utiliser les 
méthodes fournies par vue, mais ces méthodes sont destinées à la logique
 des données au lieu de traiter les événements DOM.  Vue fournit 
ci-dessous des modificateurs d'événement pour v-on et ces modificateurs 
sont des suffixes de directive indiqués par un point.

1. .stop
2. .prevent
3. .capture
4. .self
5. .once
6. .passive

Prenons un exemple de stop modificateur,

```jsx
<!-- the click event's propagation will be stopped -->
<a v-on:click.stop="methodCall"></a>
```

Vous pouvez également enchaîner les modificateurs comme ci-dessous,

```jsx
<!-- modifiers can be chained -->
<a v-on:click.stop.prevent="doThat"></a>
```