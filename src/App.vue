<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  methods: {
    deepClone(target) {
      if(typeof(target) !== `object`) return target
      let result
      if(Object.prototype.toString.call(target) === `[object Array]`) {
        result = []
      } else {
        result = {}
      }
      for (const key in target) {
        if (target.hasOwnProperty(key)) {
          result[key] = this.deepClone(target[key])
        }
      }
      return result
    }
  },
  components: {
    HelloWorld
  }
}
</script>
