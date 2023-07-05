# Comment chaîner les filtres ?

Relue ?: No

Vous pouvez 
enchaîner les filtres les uns après les autres pour effectuer plusieurs 
manipulations sur l'expression.  La structure générique de la chaîne de 
filtrage serait comme ci-dessous,

```jsx
{{ message | filterA | filterB | filterB ... }}
```

Dans la pile de 
chaînes ci-dessus, vous pouvez observer cette expression de message 
appliquée avec trois filtres, chacun séparé par un symbole pipe (|).  Le
 premier filtre (filtreA) prend l'expression comme un seul argument et 
le résultat de l'expression devient un argument pour le second filtre 
(filtreB) et la chaîne continue pour les filtres restants.

Par exemple, si 
vous souhaitez transformer une expression de date avec un format de date
 complet et des majuscules, vous pouvez appliquer les filtres dateFormat
 et majuscules comme ci-dessous,

```jsx
{{ birthday | dateFormat | uppercase }}
```