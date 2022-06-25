<template>
  <div id="app" class="screen-area">
    <time-picker v-model="selectedTime"/>
  </div>
</template>

<script>
import TimePicker from "@/components/TimePicker";

export default {
  name: 'App',
  data(){
    return {
      selectedTime: {
        hours: 23,
        minutes: 59,
      }
    }
  },
  components: {
    TimePicker
  }
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
.screen-area{
  width: 360px;
  height: 360px;
}
</style>
