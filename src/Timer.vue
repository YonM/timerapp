<template>
<div>
  <h1 :class="{ 'red-text': complete }">{{value}}</h1>
  <button @click="start">Start Timer!</button>
  <button @click="stop">Stop</button>
  <button @click="reset">Reset</button>
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
      value: this.time,
      timer: undefined,
      complete: false,
    }
  },
  methods: {
    start: function() {
      this.complete = false;
      this.timer = setInterval(_ => {
        this.value = this.value - 1;
        if (this.value === 0) {
          clearInterval(this.timer);
          this.complete = true;
        }
      }, 1000);
    },
    stop: function() {
      this.complete = false;
      clearInterval(this.timer);
    },
    reset: function() {
      this.stop();
      this.value = this.time;
    }
  }
}  
</script>

<style>
  .red-text {
    color: red;
  }
</style>
