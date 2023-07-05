# Quelle est la différence entre les versions complètes et d'exécution uniquement ?

Relue ?: No

Il existe deux types de builds fournis par VueJS,

**1. Complète :**  Ce sont les versions qui contiennent à la fois le compilateur et le runtime.

**2. Runtime Only :** 
 Ces builds n'incluent pas le compilateur mais le code est responsable 
de la création des instances de Vue, du rendu et des correctifs du DOM 
virtuel.   Ce sont environ 6 Ko plus légers min + gzip.