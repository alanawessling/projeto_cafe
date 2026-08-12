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
<style scoped>
.home { 
text-align: center; 
padding: 70px 20px; 
} 
.home h1 { 
font-size: 35px;
color: #673411
} 
.home p { 
font-size: 18px; 
margin-bottom: 25px; 
} 
.home button { 
background: #673411; 
color: white; 
border: none; 
padding: 12px 20px; 
margin: 5px; 
border-radius: 6px; 
}
</style>