<script setup>
import { ref } from 'vue' 
import Home from './HomeVue.vue' 
import Avaliacao from './AvaliacaoVue.vue' 
import Ranking from './RankingVue.vue' 

var pagina = ref('home') 
var cafes = ref([ { nome: 'Café Especial', produtor: 'José', nota: 9.8 },
 { nome: 'Café da Serra', produtor: 'Maria', nota: 9.5 },
 { nome: 'Café do Vale', produtor: 'Pedro', nota: 9.2 } ])

function addCafe(cafe) { 
cafes.value.push(cafe) 
pagina.value = 'ranking' 
}
</script>

<template>
  <div>
    <h2>Coffee Quality</h2> 
     
    <button @click="pagina = 'home'"> Home </button>
    <button @click="pagina = 'avaliacao'"> Avaliação </button>
    <button @click="pagina = 'ranking'"> Ranking </button> 
  </div>

  <Home v-if="pagina == 'home'"
  @pagAvaliacao="pagina = 'avaliacao'"
  @pagRanking="pagina = 'ranking'" 
  /> 
  
  <Avaliacao v-if="pagina == 'avaliacao'"
  @addCafe="addCafe" 
  />
  <Ranking v-if="pagina == 'ranking'" 
  :cafes="cafes" 
  />

</template>

<style scoped>
body { 
  margin: 0; 
  font-family: Arial; 
  }
div { 
  background: white;
  padding: 15px; 
  text-align: center; 
  }
  div button { 
  background: none; 
  border: none; 
  margin: 5px 10px; 
  padding: 8px; 
  } 
</style>
