<template>
<div>
  <h1>{{value}} </h1>
  <button @click="value-=1">Start Timer! </button>
</div>
</template>

<script>
var T= {
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
    countdown: () => {
      setInterval(function() {
        this.value = this.value - 1;
        console.log("countdown initiated from: " + this.value + " " + this.time);
      }, 1000);
    }
  }
}  
export default T;  
  
</script>

<style></style>
