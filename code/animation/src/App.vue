<template>

<span> {{currentValue}}% of the CO<sub>2</sub> emitted by your purchase will be compensated.</span>
      <div class="slider-component">
        <div class="slidecontainer">
          <input
            ref="input"
            v-model="currentValue"
            type="range"
            :min="min"
            :max="max"
            class="slider"
            @input="onInput"
          >
        </div>
      </div>

  <div class="w3-container">
    <button @click="show = !show">
      Confirm
    </button>
  </div>

  <transition name="slide-fade">
    <p v-if="show">
      <img alt="materials" src="./assets/cloud_materials.png" width="255" height="330">
      <img alt="endoflife" src="./assets/cloud_endoflife.png" width="255" height="255">
      <img alt="transportation" src="./assets/cloud_transportation.png" width="255" height="255">
      <img alt="production" src="./assets/cloud_production.png" width="165" height="255">
    </p>
  </transition>

  <div class="w3-container">
  <img alt="materials1" src="./assets/cloud_materials.png" width="{{255*(1 - currentValue/100)}}" height="{{330*(1 - currentValue/100)}}">
  <img alt="endoflife1" src="./assets/cloud_endoflife.png" width="255*(1 - currentValue/100)" height="255*(1 - currentValue/100)">
  <img alt="transportation1" src="./assets/cloud_transportation.png" width="255*(1 - currentValue/100)" height="255*(1 - currentValue/100)">
  <img alt="production1" src="./assets/cloud_production.png" width="165*(1 - currentValue/100)" height="255*(1 - currentValue/100)">
  </div>


</template>

<script>
export default {
  name: 'App',
  components: {
  },

  data() {
    return{
      show: true,
      currentValue: 50,
    };
  },
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

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(-350px);
  opacity: 0;
}
</style>
