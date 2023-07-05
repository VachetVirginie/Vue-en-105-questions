# Que sont les modificateurs de clé ?

Relue ?: No

Vue prend en charge les modificateurs de clé sur `v-on`pour gérer les événements du clavier.  Prenons un exemple d'événement keyup avec enter keycode.

```jsx
<!-- only call `vm.show()` when the `keyCode` is 13 -->
<input v-on:keyup.13="show">
```

Se souvenir de tous les codes clés est vraiment difficile.  Il prend en charge la liste complète des alias de codes clés

1. .enter
2. .tab
3. .delete (captures both “Delete” and “Backspace” keys)
4. .esc
5. .space
6. .up
7. .down
8. .left
9. .right

Maintenant, l'extrait de code keyup ci-dessus peut être écrit avec des alias comme suit,

```jsx
<input v-on:keyup.enter="submit" />
<!-- OR with shorthand notation -->
<input @keyup.enter="submit" />
```

**Remarque :**  L'utilisation des événements keyCode est obsolète et peut ne pas être prise en charge dans les nouveaux navigateurs.