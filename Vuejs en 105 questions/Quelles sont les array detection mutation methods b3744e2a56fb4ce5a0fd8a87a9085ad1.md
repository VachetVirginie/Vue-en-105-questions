# Quelles sont les array detection mutation methods?

Relue ?: No

Comme son nom l'indique, les méthodes de mutation modifient le tableau d'origine.

Vous trouverez ci-dessous la liste des méthodes de mutation de tableau qui déclenchent les mises à jour de la vue.

1. push()
2. pop()
3. shift()
4. unshift()
5. splice()
6. sort()
7. reverse()

Si vous effectuez l'une des méthodes de mutation ci-dessus sur la liste, cela déclenche la
 mise à jour de la vue.  Par exemple, la méthode push sur le tableau 
nommé 'items' déclenche une mise à jour de la vue,

```jsx
vm.todos.push({ message: 'Baz' })
```