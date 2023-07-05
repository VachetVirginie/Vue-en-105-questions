# Quel est le but de la balise keep alive ?

Relue ?: No

La balise Keep-alive est un composant abstrait utilisé pour préserver l'état du 
composant ou éviter un nouveau rendu.  Lorsque vous enroulez une balise 
autour d'un composant dynamique, il met en cache les instances de 
composants inactifs sans les détruire.

Voyons l'exemple d'utilisation de celui-ci,

```jsx
<!-- Inactive components will be cached! -->
<keep-alive>
  <component v-bind:is="currentTabComponent"></component>
</keep-alive>
```

Lorsqu'il y a plusieurs enfants conditionnels, il faut qu'un seul enfant soit rendu à la fois.

```jsx
<!-- multiple conditional children -->
<keep-alive>
  <comp-a v-if="a > 1"></comp-a>
  <comp-b v-else></comp-b>
</keep-alive>
```

> **Remarque :** 
 N'oubliez pas que la balise keep-alive ne restitue pas un élément DOM 
lui-même et n'apparaît pas dans la chaîne parent du composant.
>