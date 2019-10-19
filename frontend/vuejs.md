# Vuejs cheatsheet

### installation
```
npm install vue 
npm install -g vue-cli

vue init webpack project-name
```

### Just go here
https://vuejs-templates.github.io/webpack/
https://marozed.ma/vue-cheatsheet/

### NPM clis
```
npm run dev
npm run build
npm run unit
npm run e2e
npm run lint
```

### Phpstorm .vue
https://medium.com/codeartisan/vue-js-webpack-and-phpstorm-webstorm-preparation-of-environment-22d4f92f0db5


## Templating
credit : https://devhints.io/vue
### Lists
```
<li v-for="todo in todos">
  {{ todo.text }}
  {{ $index }}
</li>
```

### Events
```<button v-on:click='submit'>Go</button>
Components
new Vue({
  components: { app: App }
})
```

### API
```
Vue.extend({ ... })        // creating components
Vue.nextTick(() => {...})
Vue.set(object, key, val)  // reactive
Vue.delete(object, key)
Vue.directive('my-dir', { bind, update, unbind })
// <div v-my-dir='...'></div>

Vue.elementDirective('my-dir', { bind, update, unbind })
// <my-dir>...</my-dir>

Vue.component('my-component', Vue.extend({ .. }))

Vue.partial('my-partial', '<div>hi {{msg}}</div>')
// <partial name='my-partial'></partial>
```
```
new Vue({
  data: { ... }
  props: ['size'],
  props: { size: Number },
  computed: { fullname() { return this.name + ' ' + this.lastName } },
  methods: { go() { ... } },
  watch: { a (val, oldVal) { ... } },
  el: '#foo',
  template: '...',
  replace: true, // replace element (default true)

  // lifecycle
  created () {},
  beforeCompile () {},
  compiled () {},
  ready () {}, // $el is inserted for the first time
  attached () {},
  detached () {},
  beforeDestroy () {},
  destroyed () {},

  // options
  directives: {},
  elementDirectives: {},
  filters: {},
  components: {},
  transitions: {},
  partials: {}
})
```
Vue templates

Via vueify
```
// app.vue
<template>
  <h1 class="red">{{msg}}</h1>
</template>
 
<script>
  module.exports = {
    data () {
      return {
        msg: 'Hello world!'
      }
    }
  }
</script> 
```
Also
```
<template lang='jade'>
h1(class='red') {{msg}}
</template>
```