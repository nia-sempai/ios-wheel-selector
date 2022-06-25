<template>
  <div class="time-selector">
    <div class="time-selector__hours">
      <wheel-selector
          :items="hoursSource"
          v-model="time.hours"
      />
    </div>
    <div class="time-selector__minutes">
      <wheel-selector
          v-model="time.minutes"
          :items="hoursSource"
      />
    </div>
  </div>
</template>

<script>
import WheelSelector from "@/components/WheelSelector";

export default {
  name: "TimePicker",
  components: {WheelSelector},
  data() {
    return {
      time: {
        hours: 0,
        minutes: 0,
      }
    }
  },
  computed: {
    hoursSource() {
      const source = [];
      for (let i = 0; i < 24; i++) {
        source.push(i);
      }
      return source;
    },
    minutesSource() {
      const source = [];
      for (let i = 0; i < 59; i++) {
        source.push(i);
      }
      return source;
    }
  }
}
</script>

<style scoped>
.time-selector {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
}
.time-selector__hours{
  width:100px;
}
.time-selector__minutes{
  width:100px;
}
</style>