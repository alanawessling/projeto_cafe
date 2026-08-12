<script setup>
</script>
<template>
    <div class="home">
         
        <h1>Coffee Quality Challenge</h1>

          <p>Campeonato de Avaliação da Qualidade do Café </p> 

          <button @click="$emit('pagAvaliacao')"> Avaliar Café </button> 
          <button @click="$emit('pagRanking')"> Ver Ranking </button>

    </div>
</template>
<style scoped></style>