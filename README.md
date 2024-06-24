# simple-vue-stepper

## Install
```
npm install vue-stepper-component --save
```

## Usage
To use the component in your templates, simply import and register with your component. To control the Stepper state, we use the v-model directive, just like on any other input element with two-way binding.

Template
```js
<v-stepper ref="stepper" :steps="steps" v-model="step"></v-stepper>

<template v-if="step === 1"><!-- Step 1 Content --></template>
<template v-if="step === 2"><!-- Step 2 Content --></template>
<template v-if="step === 3"><!-- Step 3 Content --></template>

<!-- Stepper Controls -->
<button type="button" @click="$refs.stepper.previous()">Previous</button>
<button type="button" @click="$refs.stepper.next()">Next</button>
<button type="button" @click="$refs.stepper.reset()">Reset</button>
```

Script
```js
import { VStepper } from 'vue-stepper-component'

export default {
  components: {
    VStepper
  },
  data: () => ({ steps: 3, step: undefined })
}
```
## Props
```js
/**
 * Contains the current step value. Very similar to a
 * `value` attribute on an input. In most cases, you'll want
 * to set this as a two-way binding, using the `v-model` directive.
 * @type {Number||undefined||null}
 */
value: {
  type: Number,
  default: 1
},

/**
 * Contains the steps count.
 * @type {Number}
 */
steps: {
  type: Number,
  default: 0
},

/**
 * Sets up the Stepper in either
 * linear or random mode.
 * @type {Boolean}
 */
linear: {
  type: Boolean,
  default: false
},

/**
 * Sync state with storage?
 * @type {Boolean}
 */
persist: {
  type: Boolean,
  default: false
},

/**
 * Which Storage API to use.
 * Should be used with `persist` prop.
 * @type {String}
 */
storekeeper: {
  type: String,
  default: 'localStorage',
  validator(value) {
    return ['localStorage', 'sessionStorage'].includes(value)
  }
},

/**
 * Add/Remove a divider to/from each Step component.
 * @type {Boolean}
 */
withDivider: {
  type: Boolean,
  default: true
},

/**
 * Steps wrapper component.
 * @type {Object}
 */
rootComponent: {
  type: Object,
  default: () => VStepperRoot
},

/**
 * Sets up debug mode, which reveals
 * the actual radio-button behind each step.
 * @type {Boolean}
 */
debug: {
  type: Boolean,
  default: false
}
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Build library
```
npm run build-lib
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
