<template>

  <div>
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
  </div>

  <div class="CloudImage">
    <img :src="url" @load="setheight" :style="{ height: imageHeight + 'px' }">
  </div>

</template>

<script>
import cloud_with_face from "./assets/cloud_with_face.png" 


export default {
  name: 'Ap%p',

  props: {
    SliderValue: {
      default: 100,
      type: Number,
      required: true
    },
    min: {
      default: 10,
      type: Number,
      required: true
    },
    max: {
      default: 500,
      type: Number,
      required: true
    }
  },

  data() {
    return{
      url: 'http://via.placeholder.com/200x200',
      image: cloud_with_face,
      imageHeight: null,
      currentValue: this.SliderValue
    };
  },
  
  methods: {
    setheight() {
      this.imageHeight = parseInt(this.currentValue);
      },
    onInput() {
       this.imageHeight = parseInt(this.currentValue);
      // this.currentValue is a string because HTML is weird
      this.$emit('input', parseInt(this.currentValue));
    }
  }
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 100px;
  margin-left: 100px;
  margin-right: 100px;
}

.CloudImage div{
  height: 50px
}
</style>
