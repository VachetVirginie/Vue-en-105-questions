# Quelles sont les fonctions de hook fournies par les directives ?

Relue ?: No

Un objet directive peut fournir plusieurs fonctions de crochet,

1. bind : Cela se produit une fois que la directive est attachée à l'élément.
2. inserted : ce hook se produit une fois que l'élément est inséré dans le DOM parent.
3. update : ce hook est appelé lorsque l'élément est mis à jour, mais que les enfants n'ont pas encore été mis à jour.
4. componentUpdated : ce hook est appelé une fois que le composant et les enfants ont été mis à jour.
5. unbind : ce hook n'est appelé qu'une seule fois lorsque la directive est supprimée.

**Remarque :**  plusieurs arguments peuvent être passés aux hooks ci-dessus.