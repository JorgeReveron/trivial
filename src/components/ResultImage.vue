<template>
  <h1> {{ result }}</h1>
  <img :src="imageUrl" alt="result">
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps(["result"]);
const imageUrl = ref("");

async function getImage() {
  try {
    const response = await fetch("https://yesno.wtf/api?force=" + props.result);
    const json = await response.json();
    imageUrl.value = json.image;
  } catch (error) {
    console.log(error);
  }

}

onMounted(() => {
  getImage();
});

</script>

<style scoped>
  
</style>