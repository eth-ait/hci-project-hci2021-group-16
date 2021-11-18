<template>
<div @click="taskClicks++">
  <div class="testingData" v-if="tryNumber === 1">
    <h2>Input method 1=s, 2=cb, 3=val = {{abc_arr}}</h2>
    <h2>Completion time ms = {{taskTimeArr}}</h2>
    <h2>Clicks = {{taskClicksArr}}</h2>
    <h2>Selected Compensation % {{taskCompensation}}</h2>
    <h2>provided Budget for comp. CHF {{taskBudget}}</h2>
    <h2>Transport kg = {{taskTransportEmission}}</h2>
    <h2>Material kg = {{taskMaterialEmissions}}</h2>
    <h2>Production kg = {{taskProductionEmission}}</h2>
    <h2>EOL kg = {{taskEOLEmission}}</h2>
  </div>

  <div class="budget">
    <span>Your current shopping cart is priced at {{ shoppinCartPrice }} CHF and emitted {{ co2total }} Kg of CO<sub>2</sub>.</span>
    <br>
    <h3> Your total budget is {{ totaBudget }} CHF.</h3>
  </div>

  <div class="imagecontainer">
    <div class="CloudImage">
      <img :src="url" @load="setheight" :style="{ height: imageHeight + 'px' }">
    </div>
  </div>

  <div>

    <!-- for testing only -->
    <div v-show="false" class="valuecontainer">
      <h3> {{currentValue}}% of the CO<sub>2</sub> emittet by your purchase will be compensated.</h3>
    </div>

    <template v-if="abc ===  1" class="SliderInput">
      <span> {{currentValue}}% of the CO<sub>2</sub> emittet by your purchase will be compensated.</span>
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
    </template>

    <template v-if="abc ===  2" class="CheckboxInput">
      <span>Pick your desired CO2-compensation percentage.</span>
      <br>
      <input type="radio" id="0%" value="0" v-model="currentSelected" @change="onInput">
      <label for="0%">0%   </label>
      <input type="radio" id="25%" value="25" v-model="currentSelected" @change="onInput">
      <label for="25%">25%  </label>
      <input type="radio" id="50%" value="50" v-model="currentSelected" @change="onInput">
      <label for="50%">50%  </label>
      <input type="radio" id="75%" value="75" v-model="currentSelected" @change="onInput">
      <label for="75%">75%  </label>
      <input type="radio" id="100%" value="100" v-model="currentSelected" @change="onInput">
      <label for="100%">100%  </label>
      <input type="radio" id="125%" value="125" v-model="currentSelected" @change="onInput">
      <label for="125%">125%  </label>
    </template>

    <template v-if="abc ===  3" class="ValueInput">
      <span>Input your desired CO<sub>2</sub>-compensation percentage. (Ranging from 0% to 125%.)</span>
      <br>
      <br>
      <input v-model="currentInputfield" placeholder="100.00" @change="onInput"> %
      <br>
    </template>
    
    <div class="pricecontainer">
      <br>
      <span>This will add {{currentPrice}} CHF to your bill and compensate {{ compCo2 }} Kg of CO<sub>2</sub>.</span>
      <br>
      <h3> Your total checkout price will be {{ checkoutPrice }} CHF.</h3>
    </div>
  </div>

  <div class="confirmButtom">
    <button v-on:click="confirm">Confirm</button>
  </div>

</div>
</template>



<script>
import cloud_with_face from "./assets/tornado_reoriented.png" //image to scale with compensation percentage

export default {
  name: 'Ap%p',

  props: {
    SliderValue: {
      default: 0,
      type: Number,
      required: true
    },
    min: {
      default: 0,
      type: Number,
      required: true
    },
    max: {
      default: 125,
      type: Number,
      required: true
    },

    tryNumer_: {
      default: 0,
      type: Number,
      required: true
    },

    currentSelected_: {
      default: 0,
      type: Number,
      required: true
    },
    currentInputfield_: {
      default: 0,
      type: Number,
      required: true
    },
  },

  data() {
    return{
      url: cloud_with_face,
      image: cloud_with_face,
      imageHeight: null,

      currentValue: this.SliderValue,
      currentSelected: this.currentSelected_,
      currentInputfield: this.currentInputfield_,

      currentPrice: null,
      co2budget: null,
      abc: null,
      pickedCo2Comp: null,
      checkoutPrice: null,
      compCo2: 0,

      abc_arr: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      tryNumber: this.tryNumer_,

      shoppinCartPrice: 150, //defaul, will be randomized
      minCart: 0,
      maxCart: 300,

      co2total: 0, //default, will be randomized
      co2arr: [0, 0, 0, 0],
      minCo2: 1,
      maxCo2: 100,
      co2price: 0.05, //Price per kg of co2 (according to klima-kollekte: 0.027 CHF/kg) here approx 0.05

      maxBudget: null,
      minBudget: null,
      totaBudget: null,

      taskTimeStart: null,
      taskTimeArr: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskClicks: 1,
      taskClicksArr: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskCompensation: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskBudget: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],

      taskTransportEmission: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskProductionEmission: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskEOLEmission: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
      taskMaterialEmissions: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
    };
  },
  
  methods: {

    setheight() {
      this.imageHeight = 2.5*parseInt(this.currentValue)+50;
      },

    onInput() {
      if (this.abc === 2){
        this.currentValue = this.currentSelected;
      }

      if (this.abc === 3){
        //test for input validity in input field
        if (parseFloat(this.currentInputfield) < 0 | parseFloat(this.currentInputfield) > 125 | isNaN(parseFloat(this.currentInputfield))){
          alert('Please input a number between 0% and 125%!');
          this.currentInputfield = 0;
        }
        else {
          this.currentInputfield = Math.floor(parseFloat(this.currentInputfield) * 100)/100;
          this.currentValue = this.currentInputfield;
        }
      }


      this.imageHeight = 2.5*parseFloat(this.currentValue)+50;
      this.currentPrice = Math.ceil((parseFloat(this.currentValue)/100 * this.co2total * this.co2price)*20)/20;
      this.checkoutPrice = Math.ceil(((this.currentPrice + this.shoppinCartPrice)*20))/20; //float correction
      this.compCo2 = Math.floor((this.currentPrice / this.co2price)*100)/100;

      // this.currentValue is a string because HTML is weird
      //this.$emit('input', parseInt(this.currentValue));
    },

    confirm() {
      if (this.currentPrice > this.co2budget) {
        alert('Your checkout amount of ' + (this.checkoutPrice) + ' CHF is over your budget of ' + (this.totaBudget) +' CHF!\nPlease select a different compensation percentage.')
      }
      else if (parseFloat(this.currentInputfield) < 0 | parseFloat(this.currentInputfield) > 125 | isNaN(parseFloat(this.currentInputfield))) {
        this.currentInputfield = 0;
      }
      else {
        alert('Thank you for your Purchase! :)')

        //save all relevant data for study
        this.saveData();

        //reset variables
        this.currentValue = 0;

        this.currentInputfield = 0;
        this.currentSelected = 0;

        this.tryNumber += 1; // advance tryNumber for Input selection
        if (this.tryNumber === 15){
          alert('Testing finished.\n Thank you for your participation.');
        }
        else {
          this.onInput();

          //generate new cart, budget
          this.selectInput();
          this.produceCart();
          this.produceNewBudget();
        }

        //window.location.reload(); // reload page on successful "purchase"
      }
    },

    saveData() {
       //save task time
        let taskTimeEnd = new Date().getTime();
        this.taskTimeArr[this.tryNumber] = (taskTimeEnd - this.taskTimeStart);
        this.taskTimeStart = taskTimeEnd;

        //save task clicks
        this.taskClicksArr[this.tryNumber] = this.taskClicks;
        this.taskClicks = 0;

        //save co2 array !!!compare with clouds for correct asignement!!!
        this.taskTransportEmission[this.tryNumber] = this.co2arr[0];
        this.taskMaterialEmissions[this.tryNumber] = this.co2arr[1];
        this.taskProductionEmission[this.tryNumber] = this.co2arr[2];
        this.taskEOLEmission[this.tryNumber] = this.co2arr[3];

        //save selected compensation
        this.taskCompensation[this.tryNumber] = parseInt(this.currentValue);

        //save budget
        this.taskBudget[this.tryNumber] = this.co2budget;
    },

    produceCart() {
      this.shoppinCartPrice = Math.ceil((Math.random() * (this.maxCart - this.minCart) + this.minCart)*20)/20;
      for (let i = 0; i < 4; i++){
        this.co2arr[i] = Math.ceil(Math.random() * (this.maxCo2 - this.minCo2) + this.minCo2);
        this.co2total += this.co2arr[i];
      }
    },

    produceNewBudget() {
      //Math.random() returns number in [0,1) (never 1)
      this.maxBudget = this.co2total * this.co2price * 1.25;
      this.minBudget = this.co2total * this.co2price * 0.25;

      this.co2budget = Math.ceil((Math.random() * (this.maxBudget - this.minBudget) + this.minBudget)*20)/20;
      this.totaBudget = Math.ceil(((this.co2budget + this.shoppinCartPrice)*20))/20; //float correction

      this.currentPrice = Math.ceil((parseFloat(this.currentValue)/100 * this.co2total * this.co2price)*20)/20;
      this.checkoutPrice = Math.ceil(((this.currentPrice + this.shoppinCartPrice)*20))/20; //float correction
    },

    selectInput() {
      //this.abc = Math.ceil(Math.random() * 3); //random, without respect to 5,5,5 distribution

      this.abc = this.abc_arr[this.tryNumber];
    },

    generateInputArray() {
      for (let i = 0; i < (this.abc_arr.length/3); i++) {
        let rand1 = Math.round(Math.random()*2+1);// 1, 2 or 3
        let rand2 = Math.round(Math.random()+1); // 1 or 2
        let rand3 = 0;

        if(rand1 === 1){
          rand2 += 1;
        }
        else if(rand1 === 2){
          if(rand2 === 2){
            rand2 += 1;
          }
        }

        if(rand1 != 1 & rand2 != 1){
          rand3 = 1;
        }
        else if(rand1 != 2 & rand2 != 2){
          rand3 = 2;
        }
        else if(rand1 != 3 & rand2 != 3){
          rand3 = 3;
        }

        this.abc_arr[3*i] = rand1;
        this.abc_arr[3*i+1] = rand2;
        this.abc_arr[3*i+2] = rand3;

      }
    },
  },

  //function called on mount of website
  mounted: function() {
    this.produceCart();
    this.produceNewBudget();

    this.generateInputArray();
    this.selectInput();
    this.taskTimeStart = new Date().getTime();
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

.slider-component .slidecontainer {
	width: 100%;
  height: 50px;
}

.slider-component .slidecontainer .slider {
	-webkit-appearance: none;
	appearance: none;
	width: 80%;
	height: 4px;
	border-radius: 2px;
	background: #c2c2c2;
	outline: none;
	opacity: 0.7;
	-webkit-transition: .2s;
	transition: opacity .2s;
}

.slider-component .slidecontainer .slider:hover {
	opacity: 1;
}

.slider-component .slidecontainer .slider::-webkit-slider-thumb {
	-webkit-appearance: none;
	appearance: none;
	width: 18px;
	height: 18px;
	background: #0f7a0f;
	cursor: pointer;
	border-radius: 50%;
}

.slider-component .slidecontainer .slider::-moz-range-thumb {
	width: 18px;
	height: 18px;
	background: #0f7a0f;
	cursor: pointer;
	border-radius: 50%;
}

.imagecontainer {
  height: 500px;
}

.imagecontainer .CloudImage {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 500px;
}
</style>
