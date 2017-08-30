<template>
  <div id="recherche">
  	<form v-on:submit.prevent="send">
      <input v-model="titre" id="search" type="text" placeholder="Entrez le titre de la série">
      <button id="envoi" type="submit">Rechercher une série</button>
  	</form>
  </div>
</template>

<script>
export default {
  name: 'recherche',
  
  data(){
  	return {
  		titre: ""
  	}
  },

  methods: {
    send() {
		this.$emit('send', this.titre);
			
    }
  }
}
</script>

<style>
#recherche {
	text-align: center;
}

#search {
  width: 30%;
}

#envoi, #search  {
  border-radius: 5px;
  height: 30px;
  margin-left: 1em;
}
#envoi:hover {
	cursor: pointer; 
}

</style>