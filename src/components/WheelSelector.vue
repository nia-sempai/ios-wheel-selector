<template>
  <div class="wheel-wrapper">
    <div
        class="wheel-selector"
    >
      <div
          v-text="item"
          class="wheel-selector-item"
          :key="index"
          v-for="(item,index) in items"
          v-appear.toggle="{
            toggle: true,
            callback: testCallBack
          }"
      >
      </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue';
import VueAppear from 'vue-appear'
function onAppear(appear) {
  console.log('onappear',appear)
}
Vue.use(VueAppear,{
  delay: 500,
  callback: onAppear,
  hook: 'onCenter'
})

export default {
  name: "WheelSelector",
  props: {
    items: Array,
    value: Number,
  },
  methods: {
    testCallBack(e) {
      console.log('eee', e);
    }
  }
}
</script>

<style scoped>
.wheel-wrapper {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.wheel-selector {
  width: 100%;
  height: 60px;
  background-color: lightblue;
  overflow-y: scroll;
  padding-right: 17px; /* Increase/decrease this value for cross-browser compatibility */
  box-sizing: content-box; /* So the width will be 100% + 17px */
}

.wheel-selector-item {
  pointer-events: none;
  width: 100%;
  padding: 15px 0;
}
</style>