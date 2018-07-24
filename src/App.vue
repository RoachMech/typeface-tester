<template>
  <div id="app">
    <h1>Wij zijn 30 enthousiastelingen die willen werken aan jouw online succes</h1>
    <p>Eerste alinea met tekst</p>
    <h2>Online succes</h2>
    <p>Online succes alinea met tekst</p>
  </div>
</template>

<script>
  import WebFont from 'webfontloader';

  export default {
      name: 'app',
      mounted() {
          WebFont.load({
              google: {
                  families: ['Droid Sans', 'Droid Serif']
              }
          });
      }
  }
</script>

<style lang="scss">
#app {
  font-family: 'Droid Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
  margin-top: 60px;
}
</style>
