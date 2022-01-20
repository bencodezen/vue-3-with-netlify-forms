<script setup>
import { onMounted, reactive, ref } from 'vue'

defineProps({
  msg: String
})

const data = reactive({
  name: '',
  email: '',
  message: ''
})

const elFeedbackForm = ref(null)

const encode = data => {
  return Object.keys(data)
    .map(key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
    .join('&')
}

const submitForm = () => {
  fetch('/', {
    method: 'POST',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: encode({
      'form-name': 'feedback',
      ...data
    })
  })
    .then(() => console.log('Form successfully submitted'))
    .catch(error => alert(error))
}
</script>

<template>
  <h1>Vue 3 + Netlify Forms</h1>

  <form
    class="feedback-form"
    name="feedback"
    ref="elFeedbackForm"
    @submit.prevent
  >
    <input type="hidden" name="form-name" value="feedback" />

    <div class="input-wrapper">
      <label for="name">Name</label>
      <input
        id="name"
        v-model="data.name"
        type="text"
        placeholder="Your Name"
      />
    </div>

    <div class="input-wrapper">
      <label for="email">Email</label>
      <input
        id="email"
        v-model="data.email"
        type="email"
        placeholder="yourname@domain.extension"
      />
    </div>

    <div class="input-wrapper">
      <label for="message">Message</label>
      <textarea
        id="message"
        v-model="data.message"
        placeholder="What would you like to share?"
      />
    </div>

    <button type="submit" @click="submitForm">Submit</button>
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

.input-wrapper input,
.input-wrapper textarea {
  font-family: var(--primaryFont);
}

.input-wrapper input {
  padding: 10px;
  font-size: 0.9rem;
}

.input-wrapper textarea {
  height: 100px;
  padding: 10px;
  font-size: 0.9rem;
}

button {
  padding: 8px 16px;
}
</style>
