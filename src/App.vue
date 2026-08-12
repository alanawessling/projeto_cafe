<script setup>
import { ref } from 'vue' 
import Home from './HomeVue.vue' 
import Avaliacao from './AvaliacaoVue.vue' 
import Ranking from './RankingVue.vue' 

var pagina = ref('home') 
var cafes = ref([ { nome: 'Café Especial', produtor: 'José', nota: 9.8 },
 { nome: 'Café da Serra', produtor: 'Maria', nota: 9.5 },
 { nome: 'Café do Vale', produtor: 'Pedro', nota: 9.2 } ])

function adicionarCafe(cafe) { 
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

</template>

<style scoped>

</style>
