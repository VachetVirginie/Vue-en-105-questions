# Comment vous assurez-vous que l'application vue est complaint CSP ?

Relue ?: No

Certains environnements (Google Chrome Apps) interdisent l'utilisation de `new Function()`pourévaluer les expressions et les versions complètes des applications vue dépend de cette fonctionnalité pour compiler les modèles.  Pour cette 
raison, les versions complètes de l'application VueJS ne sont pas 
conformes au CSP.

Dans ce cas, vous pouvez utiliser  **des versions d'exécution uniquement** 
 avec la pile technologique Webpack + vue-loader ou Browserify + vueify à
 travers laquelle les modèles seront précompilés dans les fonctions de 
rendu.   De cette façon, vous pouvez vous assurer que les applications 
VueJS sont conformes à 100% CSP.