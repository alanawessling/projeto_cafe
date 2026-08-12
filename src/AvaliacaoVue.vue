<script setup>
import { ref } from 'vue' 

var nome = ref('')
var prod = ref('')
var nota = ref('') 
var msg = ref('') 

const emitir = defineEmits(['addCafe']) 

function salvar() { 
    if (nome.value == '' || prod.value == '' || nota.value == '') {
     msg.value = 'Preencha todos os campos.' 
     return
    } 

    var cafe = { 
    nome: nome.value, 
    produtor: prod.value, 
    nota: Number(nota.value) 
    }
 
    emitir('addCafe', cafe)

    nome.value = '' 
    prod.value = '' 
    nota.value = '' 
    msg.value = 'Avaliação enviada!' 
}
</script>
<template>
 <div class="avaliacao">
     <h1>Avaliar Café</h1>
      <p>Preencha os dados do café:</p>
      
      <input v-model="nome" type="text" placeholder="Nome do café" /> 
      <input v-model="prod" type="text" placeholder="Nome do produtor" /> 
      <input v-model="nota" type="number" min="0" step="0.1" placeholder="Nota" />
      
      <button @click="salvar"> Enviar avaliação </button> 
      <p v-if="msg"> {{ msg }} </p> 
</div> 
</template>
<style scoped>
</style>
