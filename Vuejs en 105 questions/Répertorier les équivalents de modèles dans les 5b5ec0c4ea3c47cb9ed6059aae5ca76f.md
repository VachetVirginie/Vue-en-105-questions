# Répertorier les équivalents de modèles dans les fonctions de rendu ?

Relue ?: No

VueJS fournit des alternatives propriétaires et une utilisation de javascript simple pour les fonctionnalités du modèle.

Listons-les dans un tableau pour comparaison,

| Modèles | Fonction de rendu |
| --- | --- |
| Directives conditionnelles et en boucle : v-if et v-for | Utiliser les concepts if/else et map de JavaScript |
| Biding bidirectionnelle : modèle en V | Appliquez votre propre logique JS avec la liaison de valeur et la liaison d'événement |
| Modificateurs d'événement de capture : .passive, .capture, .once et .capture.once ou .once.capture | &, !, ~ et ~ ! |
| Modificateurs d'événements et
 de touches : .stop, .prevent, .self, keys(.enter, .13) et Modifiers 
Keys(.ctrl, .alt, .shift, .meta) | Utilisez des solutions 
javascript : event.stopPropagation(), event.preventDefault(), if 
(event.target !== event.currentTarget) return, if (event.keyCode !== 13)
 return et if (!event.ctrlKey) return |
| Slots: slot attributes | Les fonctions de rendu fournissent les propriétés d'instance this.$slots et this.$scopedSlots |