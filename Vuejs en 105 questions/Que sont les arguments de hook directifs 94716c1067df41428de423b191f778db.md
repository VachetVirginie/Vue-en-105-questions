# Que sont les arguments de hook directifs ?

Relue ?: No

Tous les crochets ont `el`, `binding`, et `vnode`comme arguments.   Parallèlement à cela,  **les hooks update**  et  **componentUpdated**  exposent `oldVnode`, pour différencier l'ancienne valeur transmise de la nouvelle valeur.  Voici les arguments passés aux crochets,

1. `el`
    
    : L'élément auquel la directive est liée et il peut être utilisé pour manipuler directement le DOM.
    
2. `binding`
    
    : un objet contenant les propriétés suivantes.
    
    1. `namev-`
        
        : Le nom de la directive, sans le
        
        préfixe.
        
    2. `valuev-my-directive="1 + 1"`
        
        : La valeur transmise à la directive.  Par exemple dans
        
        , la valeur serait 2.
        
    3. `oldValue`
        
        : La 
        valeur précédente, uniquement disponible dans update et 
        componentUpdated.  Il est disponible que la valeur ait changé ou non.
        
    4. `expressionv-my-directive="1 + 1"`
        
        : L'expression de la liaison sous forme de chaîne.  Par exemple dans
        
        , l'expression serait "1 + 1".
        
    5. `arg`
        
        : L'argument passé à la directive, le cas échéant.  Par exemple, dans v-my-directive:foo, l'argument serait "foo".
        
    6. `modifiers{ foo: true, bar: true }`
        
        : Un objet contenant des modificateurs, le cas échéant.  Par exemple, dans v-my-directive.foo.bar, l'objet modificateurs serait
        
        .
        
3. `vnode`
    
    : Le nœud virtuel produit par le compilateur de Vue.
    
4. `oldVnode`
    
    : Le nœud virtuel précédent, uniquement disponible dans les hooks update et componentUpdated.
    

Les arguments peuvent être représentés schématiquement à travers les crochets comme ci-dessous:

![https://github.com/sudheerj/vuejs-interview-questions/raw/master/images/custom-directives.svg](https://github.com/sudheerj/vuejs-interview-questions/raw/master/images/custom-directives.svg)