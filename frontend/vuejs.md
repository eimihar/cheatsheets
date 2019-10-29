# Vuejs cheatsheet

## Single Page Application (SPA) installation
```
npm install vue 
npm install -g vue-cli

vue init webpack project-name
// OR for latest vue
vue create project-name
```

## Faq
#### why template data returns callback
so it is not referenced!

#### difference between props and data in template/child
data is like a private/local variable, props is like a public reference

## Just go here
https://vue-loader.vuejs.org/guide/pre-processors.html#sass
https://vuejs-templates.github.io/webpack/
https://flaviocopes.com/vue-cheat-sheet/
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

### Options
root
```
el, data, computed, watch, methods, template, replace, components
```
component
```
data, computed, watch, methods, props, template
```
### Lists
```
<li v-for="todo in todos">
  {{ todo.text }}
  {{ $index }}
</li>
```

### Events
```<button v-on:click='submit'>Go</button>
```
Components
```
new Vue({
  components: { app: App }
})
```

### Router
accessing app from router
```
router.app.$axios.defaults.headers.common['Authorization'] = '';
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

### Tips
#### Component model binding 
credit : https://vuejs.org/v2/guide/components.html

Custom events can also be used to create custom inputs that work with v-model. Remember that:
```
<input v-model="searchText">
```

does the same thing as:

```
<input v-bind:value="searchText" v-on:input="searchText = $event.target.value">
```
When used on a component, v-model instead does this:

```
<custom-input v-bind:value="searchText" v-on:input="searchText = $event"></custom-input>
```

For this to actually work though, the <input> inside the component must:

Bind the value attribute to a value prop
On input, emit its own custom input event with the new value
Here’s that in action:

```
Vue.component('custom-input', {
  props: ['value'],
  template: `
    <input
      v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)"
    >
  `
})
```

Now v-model should work perfectly with this component:

```
<custom-input v-model="searchText"></custom-input>
```

### Component slot
Insert text into the slot without going through prop binding etc
```
<alert-box>Oops</alert-box>
```
```
Vue.component('alert-box', {
  template: `
    <div class="demo-alert-box">
      <strong>Error!</strong>
      <slot></slot>
    </div>
  `
})
```

### v-bind:is
Bind with component
```
var v = new Vue({
    el: '#app',
    data: {
        component: 'the-component'
    }
});
```
```
<div id='app'>
    <component :is="component"></component>
</div>
```
