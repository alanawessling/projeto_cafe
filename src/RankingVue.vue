<script setup>

var props = defineProps(['cafes'])
var cafes = props.cafes

for (var i = 0; i < cafes.length; i++) {

  for (var j = i + 1; j < cafes.length; j++) {
    
    if (cafes[j].nota > cafes[i].nota) {

      var troca = cafes[i]

      cafes[i] = cafes[j]

      cafes[j] = troca
    }
  }
}

if (cafes.length > 10) {

cafes.length = 10
}
</script>
<template>

<div class="ranking">

  <h1>Top 10 Cafés</h1>

  <div v-for="(cafe, i) in cafes" :key="i" class="cafe">

    {{ i + 1 }}º - {{ cafe.nome }} - {{ cafe.nota }}
  </div>
</div>

</template>

