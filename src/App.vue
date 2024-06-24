<template>
  <div id="app">
    <!--Usage example -->
    <v-stepper ref="stepper" :steps="steps" v-model="step"></v-stepper>
    <div style="padding: 50px;">
      <template v-if="step === 1">Step 1 Content</template>
      <template v-if="step === 2">Step 2 Content</template>
      <template v-if="step === 3">Step 3 Content</template>
    </div>
    <div>
      <button type="button" @click="$refs.stepper.previous()">Previous</button>
      <button type="button" @click="$refs.stepper.next()">Next</button>
      <button type="button" @click="$refs.stepper.reset()">Reset</button>
    </div>
  </div>
</template>

<script>
import VStepper from './components/Stepper.vue'

export default {
  name: 'App',
  components: {
    VStepper
  },
  data: () => ({ steps: 3, step: undefined })
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
  padding: 80px 0;
  width: 80%;
}
</style>
