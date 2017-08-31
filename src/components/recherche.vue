<template>
  <div id="recherche">
  	<form v-on:submit.prevent="send">
      <input v-model="titre" id="search" type="text" placeholder="Entrez le titre de la série (exemple : breaking bad)">
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
  width: 50%;
}

#envoi, #search  {
  border-radius: 5px;
  height: 40px;
  margin-left: 1em;
  font-size: 20px;
}
#envoi:hover {
	cursor: pointer; 
}

</style>