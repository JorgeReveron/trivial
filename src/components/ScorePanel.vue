<template>
  <h1>
    Nº Preguntas: {{ questionNumber }} | Puntos: {{ points }}
  </h1>
</template>

<script setup>

//Define las propiedades para la app principal
defineProps(["questionNumber", "points"])
</script>

<style scoped>
  
</style>