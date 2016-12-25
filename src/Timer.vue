<template>
<div>
  <h1>{{value}}</h1>
  <button @click="countdown">Start Timer! </button>
</div>
</template>

<script>
export default {
  name: "Timer",
  props: {
    time: Number
  }, 
  data() {
    return {
      value: this.time
    }
  },
  methods: {
    countdown: function() {
      const timer = setInterval(_ => {
        this.value = this.value - 1;
        if (this.value === 0) clearInterval(timer);
      }, 1000);
    }
  }
}  
</script>

<style></style>
