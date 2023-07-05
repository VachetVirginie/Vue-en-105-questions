# Est-il possible de passer des paramètres pour les filtres ?

Relue ?: No

Oui, vous pouvez 
passer des arguments pour un filtre similaire à une fonction javascript.
  La structure générique des paramètres de filtre serait la suivante,

```jsx
{{ message | filterA('arg1', arg2) }}
```

Dans ce cas, 
filterA prend l'expression du message comme premier argument et les 
paramètres explicites mentionnés dans le filtre comme deuxième et 
troisième arguments.

Par exemple, vous pouvez trouver la force exponentielle d'une valeur particulière

```jsx
{{ 2 | exponentialStrength(10) }} <!-- prints 2 power 10 = 1024 -->
```