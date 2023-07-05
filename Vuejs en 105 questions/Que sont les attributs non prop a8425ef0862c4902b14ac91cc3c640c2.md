# Que sont les attributs non prop ?

Relue ?: No

Un attribut non-prop est un attribut qui est passé à un composant, mais qui n'a pas de prop correspondant défini.

Par exemple, si vous utilisez un composant d'entrée personnalisé tiers qui nécessite un `data-tooltip`attribut sur l'entrée, vous pouvez ajouter cet attribut à l'instance du composant,

```jsx
<custom-input data-tooltip="Enter your input" />
```

Si vous essayez de 
transmettre les accessoires du composant parent, les accessoires enfants
 portant les mêmes noms seront remplacés.  Mais des accessoires comme `class`et `style`font exception à cela, ces valeurs seront fusionnées dans le composant enfant.

```jsx
<!-- Child component -->
<input type="date" class="date-control">

<!-- Parent component -->
<custom-input class="custom-class" />
```