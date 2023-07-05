# Comment utilisez-vous les gestionnaires d'événements ?

Relue ?: No

Vous pouvez utiliser des gestionnaires d'événements dans vue similaires au 
javascript simple.  Les appels de méthode prennent également en charge 
la variable spéciale $event.

```jsx
<button v-on:click="show('Welcome to VueJS world', $event)">
  Submit
</button>

methods: {
  show: function (message, event) {
    // now we have access to the native event
    if (event) event.preventDefault()
    console.log(message);
  }
}
```