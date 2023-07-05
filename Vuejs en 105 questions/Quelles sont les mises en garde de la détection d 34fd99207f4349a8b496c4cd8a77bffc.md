# Quelles sont les mises en garde de la détection des changements de tableau ?

Relue ?: No

Vue ne peut pas détecter les changements pour le tableau dans les deux cas ci-dessous,

1. Lorsque vous définissez directement un élément avec l'index, par exemple,
    
    ```jsx
    vm.todos[indexOfTodo] = newTodo
    ```
    
2. Lorsque vous modifiez la longueur du tableau, par exemple,
    
    ```jsx
    vm.todos.length = todosLength
    ```
    

Vous pouvez surmonter les deux mises en garde en utilisant `set`et `splice`méthodes, Voyons les solutions avec des exemples,

**Première solution de cas d'utilisation**

```jsx
// Vue.set
Vue.set(vm.todos, indexOfTodo, newTodoValue)
(or)
// Array.prototype.splice
vm.todos.splice(indexOfTodo, 1, newTodoValue)
```

**Deuxième solution de cas d'utilisation**

```jsx
vm.todos.splice(todosLength)
```