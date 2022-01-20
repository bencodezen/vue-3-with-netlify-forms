<script setup>
import { reactive } from 'vue'

defineProps({
  msg: String
})

const data = reactive({
  name: '',
  email: '',
  message: ''
})
</script>

<template>
  <h1>Vue 3 + Netlify Forms</h1>

  <form class="feedback-form">
    <div class="input-wrapper">
      <label for="name">Name</label>
      <input id="name" v-model="data.name" type="text" />
    </div>

    <div class="input-wrapper">
      <label for="email">Email</label>
      <input id="email" v-model="data.email" type="email" />
    </div>

    <div class="input-wrapper">
      <label for="message">Message</label>
      <textarea id="message" v-model="data.message"></textarea>
    </div>

    <button type="submit" @click="submit">Submit</button>
  </form>
</template>

<style scoped>
a {
  color: #42b983;
}

.feedback-form {
  max-width: 600px;
  margin: 0 auto;
}

.input-wrapper {
  display: grid;
  grid-template-rows: auto 1fr;
  grid-row-gap: 5px;
  margin-bottom: 1rem;
  text-align: left;
}

.input-wrapper:last-child {
  margin-bottom: 0;
}

.input-wrapper input {
  padding: 10px;
  font-size: 1rem;
}

.input-wrapper textarea {
  height: 100px;
}
</style>
