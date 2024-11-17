<script setup lang="ts">
import { computed, ref } from 'vue'

const clicked = ref(false)

const text = computed(function () {
  if (clicked.value) {
    return 'сосал?'
  } else {
    return 'Вы рады, что мы дружим?'
  }
})
</script>

<template>
  <div class="home">
    <div class="question">{{ text }}</div>
    <button class="answer" :clicked="clicked ? true : undefined" @click="clicked = true">Да</button>
  </div>
</template>

<style scoped>
.home {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  justify-content: space-around;
}
.question {
  width: 100%;
  font-size: 100px;
  text-align: center;
}

.answer {
  width: 40vw;
  font-size: 50px;
  background-color: aliceblue;
  border-radius: 15px;
}

.answer[clicked] {
  background-color: rgb(108, 184, 108);
}
</style>
