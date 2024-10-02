<template>
  <div>
    <h1>Current Time: {{ currentTime }}</h1>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentTime = ref("");

const updateTime = () => {
  const now = new Date();
  currentTime.value = now.toLocaleTimeString();
};

let timer = null;

onMounted(() => {
  updateTime();
  timer = setInterval(updateTime, 1000);
});

onUnmounted(() => {
  clearInterval(timer);
});
</script>

<style scoped></style>
