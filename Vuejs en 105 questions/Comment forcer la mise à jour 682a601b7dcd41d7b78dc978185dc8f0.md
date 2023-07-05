# Comment forcer la mise à jour ?

Relue ?: No

ll est extrêmement rare de devoir forcer manuellement une mise à jour malgré le fait 
qu'aucune donnée réactive n'a changé.   c'est-à-dire, forcer l'instance 
de Vue à restituer manuellement.   Vous pouvez forcer la mise à jour en 
utilisant  **vm.$forceUpdate() .**  la méthode API

> **Remarque :** 
 Cela n'affecte pas tous les composants enfants, mais uniquement 
l'instance elle-même et les composants enfants avec le contenu 
d'emplacement inséré.
>