<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div id="wrapper">
    <main id="content">
      <img alt="Vue logo" src="./assets/logo.png" style="max-width: 300px" />
      <HelloWorld />
    </main>
    <footer id="footer">
      <a href="https://github.com/bencodezen/vue-3-with-netlify-forms"
        >GitHub Repo</a
      >
      | Deployed with
      <a href="https://www.netlify.com/">Netlify</a>
    </footer>
  </div>
</template>

<style>
*,
html,
body {
  box-sizing: border-box;
}

html,
body {
  margin: 0;
  padding: 0;
}

:root {
  --primaryFont: Avenir, Helvetica, Arial, sans-serif;
}

#app {
  font-family: var(--primaryFont);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#content {
  flex: 1;
  margin-top: 30px;
}

#footer {
  padding: 30px;
}

#wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

a {
  color: #42b983;
}

button {
  padding: 8px 16px;
}
</style>
