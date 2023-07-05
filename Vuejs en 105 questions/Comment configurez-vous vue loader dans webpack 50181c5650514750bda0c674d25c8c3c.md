# Comment configurez-vous vue loader dans webpack?

Relue ?: No

La configuration de
 Vue Loader est un peu différente des autres chargeurs en ajoutant le 
plugin de Vue Loader à votre configuration webpack.  Le plugin vue 
loader est requis pour cloner toutes les autres règles (règles js et 
css) définies et les appliquer aux blocs de langue correspondants 
(<script> et <style>) dans les fichiers .vue.

Par exemple, la démonstration simple de la configuration de webpack pour vue loader serait comme ci-dessous,

```jsx
// webpack.config.js
const VueLoaderPlugin = require('vue-loader/lib/plugin')

module.exports = {
  mode: 'development',
  module: {
    rules: [
      {
        test: /\.vue$/,
        loader: 'vue-loader'
      },
      // this will apply to both plain `.js` files and `<script>` blocks in `.vue` files
      {
        test: /\.js$/,
        loader: 'babel-loader'
      },
      // this will apply to both plain `.css` files and `<style>` blocks in `.vue` files
      {
        test: /\.css$/,
        use: [
          'vue-style-loader',
          'css-loader'
        ]
      }
    ]
  },
  plugins: [
    // make sure to include the plugin for cloning and mapping them to respective language blocks
    new VueLoaderPlugin()
  ]
}
```