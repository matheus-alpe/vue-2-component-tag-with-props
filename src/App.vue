<template>
  <div id="app">
    <div>
      <img alt="Vue logo" src="./assets/logo.png" />
    </div>
    <div>
      <button @click="toggleComponent">Change Component</button>
    </div>

    <component
      :is="selectedComponent"
      msg="Welcome to Your Vue.js App"
      value="oi"
      @show-message="showMessageTemporarily"
    />


    <div v-if="showMessage">
      <p style="color: red">warning message</p>
    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import FormField from './components/FormField.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    FormField,
  },
  data() {
    return {
      selectedComponent: 'HelloWorld',
      showMessage: false
    }
  },

  methods: {
    toggleComponent () {
      this.selectedComponent = this.selectedComponent === 'FormField' ? 'HelloWorld' : 'FormField'
    },

    showMessageTemporarily() {
      console.log('message')
      this.showMessage = true

      setTimeout(() => {
        this.showMessage = false
      }, 1000)
    }
  }
}
</script>

<style>
body {
  background: #333;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FFF;
  margin-top: 60px;
}
</style>
