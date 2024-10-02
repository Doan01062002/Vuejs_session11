<template>
  <div>
    <h1>Count: {{ count }}</h1>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const count = ref(0);
let timer = null;

onMounted(() => {
  timer = setInterval(() => {
    count.value++;
  }, 1000);
});

onUnmounted(() => {
  clearInterval(timer);
});
</script>

<style scoped></style>
