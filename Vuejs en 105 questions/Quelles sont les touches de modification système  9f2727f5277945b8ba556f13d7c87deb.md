# Quelles sont les touches de modification système prises en charge ?

Relue ?: No

Vue prend en charge les modificateurs ci-dessous pour déclencher les écouteurs d'événements de la souris ou du clavier lorsque la touche correspondante est enfoncée,

1. .ctrl
2. .alt
3. .shift
4. .meta

Prenons un exemple de modificateur de contrôle avec événement click,

```jsx
<!-- Ctrl + Click -->
<div @click.ctrl="doSomething">Do something</div>
```