<template>
  <div id="app">
  <Timer :time="10"></Timer>
  </div>
</template>

<script>
import Timer from './Timer.vue';
export default {
  name: 'app',
  components: {
    Timer
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
    }
  }
}
</script>

<style>
</style>
