<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    sdfsaf
    <v-stepper :steps="steps" v-model="step"></v-stepper>
{{step}}
    <template v-if="step === 1">asdfasdfsadf<!-- Step 1 Content --></template>
    <template v-if="step === 2">asdfsdaf<!-- Step 2 Content --></template>
    <template v-if="step === 3">3333<!-- Step 3 Content --></template>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import VStepper from './components/Stepper.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    VStepper
  },
  data: () => ({ steps: 3, step: undefined })
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
