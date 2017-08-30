<template>
  <div id="fiche" v-if="someData">
    <h1>Titre : {{ someData.show_title }}</h1>
    <h2>Année de sortie : {{ someData.release_year }}</h2>
    <p>Résumé : <br>{{ someData.summary }}</p>
    <img v-bind:src=someData.poster>
  </div>
</template>

<script>
export default {
  name: 'fiche',
  props: ['someData'],
}

</script>

<style>
#fiche {
  width: 100%;
  margin: auto;
  text-align: center;
  margin-top: 1em;
  color: white;
}

p {
  width : 70%;
  margin: auto;
  margin-bottom: 1em;
}

#fiche img {
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>