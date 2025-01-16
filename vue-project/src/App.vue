<script setup>
import Clock from './components/Clock.vue'
</script>

<template>
  <div class="main">
    <Clock />
  </div>
</template>

<style scoped>
.main {
  display: flex;
  place-content: center;
  transition: 0.2s;
}
</style>
