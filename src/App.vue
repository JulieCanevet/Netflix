<template>
  <div id="app">
    <logoNetflix></logoNetflix>
    <recherche v-on:send="api"></recherche>
    <ficheSerie v-bind:someData="someData"></ficheSerie>
  </div>
</template>

<script>
import logoNetflix from './components/logoNetflix'
import recherche from './components/recherche'
import ficheSerie from './components/ficheSerie'

export default {
  name: 'app',
  components: {
    logoNetflix,
    recherche,
    ficheSerie
  },
  data(){
    return {
    someData:""
  }
},
  methods:
  { api(titre) {

  // GET /someUrl
  this.$http.get('https://netflixroulette.net/api/api.php?title='+ titre).then(response => {
    // get body data
    this.someData = response.body;
  }, response => {
    alert("recherche inconnue");
  });
}
}
}


</script>

<style>
body {
  background-color: black;
  font-family: 'Nunito', sans-serif;
}
</style>
