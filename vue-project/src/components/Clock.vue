<script setup>
import { ref } from 'vue'

let date = ref('')
let time = ref('')

/**
 * Get the current date and time.
 *
 * @returns {Object} An object with the date and time.
 * @property {string} date Formatted date string.
 * @property {string} time formatted time string.
 */
function getDateAndTime() {
  // Get the current date and time
  const date = new Date()
  const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' }
  const time = date.toLocaleTimeString('zh-CN')
  const formattedDate = date.toLocaleDateString('zh-CN', options)
  return { date: formattedDate, time }
}

// Update the date and time every second
setInterval(() => {
  const { date: _date, time: _time } = getDateAndTime()
  date.value = _date
  time.value = _time
}, 1000)
</script>

<template>
  <div class="clock green">
    <p class="date">{{ date }}</p>
    <p class="time">{{ time }}</p>
  </div>
</template>

<style scoped>
.clock {
  text-align: center;
  font-size: 2rem;
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  height: calc(100vh - 20%);
  place-content: center;
  place-items: center;
}
</style>
