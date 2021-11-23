<template>
<div class="whole" @click="taskClicks++">

  <div class="testingData" v-if="tryNumber === 15"> <!-- SET TO 15 FOR TESTS -->
    <h2>UserID = {{UserID}}</h2>
    <h2 v-if="testType == 1">Input method 1=s, 2=cb, 3=val = {{abc_arr}}</h2>
    <h2 v-if="testType == 0">Input Option 0=Checkbox, 2=Buster = {{cb_arr}}</h2>
    <h2>Completion time ms = {{taskTimeArr}}</h2>
    <h2>Clicks = {{taskClicksArr}}</h2>
    <h2>Selected Compensation % {{taskCompensation}}</h2>
    <h2>provided Budget for comp. CHF {{taskBudget}}</h2>
    <h2>Transport kg = {{taskTransportEmission}}</h2>
    <h2>Material kg = {{taskMaterialEmissions}}</h2>
    <h2>Production kg = {{taskProductionEmission}}</h2>
    <h2>EOL kg = {{taskEOLEmission}}</h2>
  </div>

    <div class="userTask">
      <h3 v-if="testType === 0">Test 1/2</h3>
      <h3 v-if="testType === 1">Test 2/2</h3>
      <br>
      <h3> <i>User Task:</i> </h3>
      <h3> <i>Your total budget is <strong>{{ totaBudget }} CHF</strong>. <br> Complete the checkout, while staying within your Budget.</i> </h3>
      <br>
      <br>
      <hr>
    </div>

  <div class="header">
    <img alt="Vue logo" src="./assets/logo.png" class="centered">
  </div>

    <h1>Check Out</h1>


    <div class="buster" v-if="checkoutType == 1">
      <div class="bustertitle">
        <h3>Your Purchase will emit {{ co2total }} Kg of CO<sub>2</sub>, let's fix that with:</h3>
        <h2> Carbon Busters </h2>
      </div>
        <div class="animation">
          <div class="character"> 
            <div class="product">
              <!-- <div class="content">
              <h1>{{product}}</h1>
              </div> -->
              <div class="container">
              <div class="variants">
                  <img v-for="variant in variants"
                  class="headshot"
                  :key="variant.variantId" 
                  @mouseout="setClickedImage()"
                  @mouseover="updateImage(variant.variantImage)"
                  @click="setImage(variant.variantImage)"
                    :src="variant.variantIcon ">
              </div>
              <div class="gemuse">
                <img class="boy" :src="productImage">
              </div>
            </div>
            </div>
          </div>

          <div class="wind"> 
            <div class="imagecontainer">
              <div ref="tornado" class="CloudImage">
                 <img :src="url" @load="setheight" :style="{ height: imageHeight + 'px' }">
              </div>
             </div>
          </div>

          <div class="clouds">
             <!-- <img ref="cloud" class="cloud" :src="productImage" @click="disappear()"> -->
            <div class="fourclouds" ref="fourclouds">
              <div class="content_img">
                <div class="type"></div>
                  <img class="transportation" src="./assets/cloud_transportation.png" :style="{ height: transportSize + '%' }" alt="CO2 emission through transportation is caused at early stages of your product's life cycle. In particular, raw materials have to be excavated and transported to the location of production. In some cases, production may be split into different locations, leading to even more transportation needed. All of this causes CO2 to be set free. Further, CO2 is emitted during the transportation of the product to your home.">
                <div class="textbox">
                  Not only the <strong>transportation</strong> of the final goods to your home causes CO2 emissions, but also the transportation between the raw material excavation site and the production locations. You purchase will set <strong>{{co2arr[0]}}kg of CO<sub>2</sub> </strong> free in relation to its transportation.
                </div>
              </div>
              <div class="content_img">
                <div class="type"></div>
                <img class="materials" src="./assets/cloud_materials.png" :style="{ height: materialSize + '%' }" alt="The production of raw material is linked to CO2 emissions through the process' energy consumption.">
                <div class="textbox">
                    The production of raw <strong>material</strong> is linked to CO2 emissions through the process' energy consumption. The materials of you purchase will contribute to <strong>{{co2arr[1]}}kg of CO<sub>2</sub> </strong> emisisons.
                </div>
              </div>
              <div class="content_img">
                <div class="type"></div>
                <img class="production" src="./assets/cloud_production.png" :style="{ height: productionSize + '%' }" align="bottom" alt="The processing of raw materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods.">
                <div class="textbox">
                  The <strong>processing</strong> of materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods. The production of you purchased goods emits <strong>{{co2arr[2]}}kg of CO<sub>2</sub> </strong>.
                </div>
              </div>
              <div class="content_img">
                <div class="type"></div>
                <img class= "endoflife" src="./assets/cloud_endoflife.png" :style="{ height: endoflifeSize + '%' }" alt="Have you ever thought oc the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.">
                <div class="textbox">
                  Have you ever thought of the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.  The <strong>end of life</strong> property of your goods contributes to  emissions.<strong>{{co2arr[3]}}kg of CO<sub>2</sub> </strong>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class= "slider_stuff">
          <div class= "slider">
            <template v-if="abc ===  1" class="SliderInput">
              <span> {{currentValue}}% of the CO<sub>2</sub> emittet by your purchase will be compensated.</span>
              <br>
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
              <span>Input your desired CO<sub>2</sub>-compensation. (0% to 125%.)</span>
              <br>
              <br>
              <input v-model="currentInputfield" placeholder="100.00" @change="onInput">
              <br>
            </template>
          </div>

          <div class= "summary">
            This will add {{currentPrice}} CHF to your bill and compensate {{ compCo2 }} Kg of CO<sub>2</sub>
          </div>
        </div>

        <div class= "totals">
          <h3> Your total checkout price will be {{ checkoutPrice }} CHF.</h3>
          <div class="confirm">
            <button v-on:click="confirm">Confirm Purchase</button>
        </div>
    </div>

    </div>

    <div class="checkbox" v-if="checkoutType == 0">
      <br>
      <br>
        <input type="checkbox" id="check%" value="100" v-model="checkboxBool" @change ="onInput">
        <label for="check%"> Compensate my emissions.  </label>
        <br>
        <br>
        <span>(This will add {{totalCompPrice}} CHF to your total.)</span>
        <br>

        <h3>Your total checkout price will be {{ checkoutPrice }} CHF.</h3>
        <div class="confirm">
            <button v-on:click="confirm">Confirm Purchase</button>
        </div>
        
    </div>

    <div class="products">
      <div class="product_title">
        <h3>Check Out Summary</h3>
      </div>
      <ul>
        <img src="./assets/image.jpg" class="product_image">
      <li>
        <p>Lenovo Laptop</p>
        <p id="price1"></p>
        <p id="comp1"></p>
      </li>
      <img src="./assets/charger.jpg" class="product_image">
      <li>
        <p>Lenovo Charger</p>
        <p id="price2"></p>
        <p id="comp2"></p>
      </li>
      <img src="./assets/mice.jpg" class="product_image">
      <li>
        <p>Lenovo Mice+Keybaord</p>
        <p id="price3"></p>
        <p id="comp3"></p>
      </li>
    </ul>
    <div>
      <h3>Subtotal: {{ shoppinCartPrice }} CHF</h3>
    </div>
  </div>
</div>



</template>

  <script>
  import cloud_with_face from "./assets/tornado_reoriented.png" //image to scale with compensation percentage

  export default {

    name: 'HelloWorld',
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


      emissionvalues:{ //no longer needed
        type: Array,
        default(){
          return [110, 70, 100, 120] /*emissions [trans mat prod eol]*/
        }
      },
    },


    data() {
      return{
        UserID: '00',
        testType: 1, //0 = checkbox or buster / 1 = different input methods

        url: cloud_with_face,
        image: cloud_with_face,
        imageHeight: null,

        currentValue: this.SliderValue,
        currentSelected: this.currentSelected_,
        currentInputfield: this.currentInputfield_,
        checkboxBool: false,

        currentPrice: null,
        co2budget: null,
        abc: null,
        checkoutType: 1,
        pickedCo2Comp: null,
        checkoutPrice: null,
        compCo2: 0,


        abc_arr: [0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],

        cb_arr: [0,0,0,0,0,0,0,0,0,0],

        tryNumber: this.tryNumer_,


        shoppinCartPrice: 150, //defaul, will be randomized
        minCart: 100,
        maxCart: 500,

        co2total: 0, //default, will be randomized
        co2arr: [0, 0, 0, 0],
        minCo2: 10,
        maxCo2: 200,
        co2price: 0.05, //Price per kg of co2 (according to klima-kollekte: 0.027 CHF/kg) here approx 0.05
        totalCompPrice: 0,

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



        transportSize: 10,
        materialSize: 10,
        productionSize: 10,
        endoflifeSize: 10,




        product: 'Carbon Busters',
        productImage: require("./assets/images/1.png"), 
        clickedImage: require("./assets/images/1.png"),
        variantIcon: require("./assets/images/a.png"),
        variants: [
          {
            variantId: 1,
            variantIcon: require("./assets/images/a.png"),
            variantImage: require("./assets/images/1.png"),
          },
          {
            variantId: 2,
            variantIcon: require("./assets/images/b.png"),
            variantImage: require("./assets/images/2.png"),
          },
          {
            variantId: 3,
            variantIcon: require("./assets/images/c.png"),
            variantImage: require("./assets/images/3.png"),
          },
        ],


        /*trans: this.emissionvalues[0],
        mat: this.emissionvalues[1],
        prod: this.emissionvalues[2],
        eol: this.emissionvalues[3],
        */
      };
    },



    methods: {

      setheight() {
        this.imageHeight = 1.3*parseFloat(this.currentValue)+15;
      },

      onInput() {
        console.log('onImput');
        if(this.testType == 1){
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
        }

        else {
          console.log('testType 0');
          if(this.checkoutType == 0){
            if(this.checkboxBool){
              this.currentValue = 100;
              console.log('true');
            }
            else{
              this.currentValue = 0;
              console.log('false');
            }
          }
        }


        this.imageHeight = 1.3*parseFloat(this.currentValue)+15;
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

          if(this.checkoutType == 1 | this.testType == 1){
            this.disappear();
            setTimeout( () => { //stuff gets executed after delay
              alert('Thank you for your Purchase! :)');
              this.reappear();
              scroll(0,0);
            }, 1200);
          }
          else{
            setTimeout( () => { //stuff gets executed after delay
              alert('Thank you for your Purchase! :)');
              scroll(0,0);
            }, 100);
          }
          //save all relevant data for study
          this.saveData();

          //reset variables
          this.currentValue = 0;

          this.currentInputfield = 0;
          this.currentSelected = 0;
          this.checkboxBool = false;

          this.tryNumber += 1; // advance tryNumber for Input selection
          if (this.tryNumber === 15 && this.testType == 1){
            alert('Testing finished.\nThank you for your participation.');
          }
          else if(this.tryNumber === 10 && this.testType == 0){
            alert('First test finished.\nPlease hand over the device to the tester.');
            this.tryNumber = 15;
          }
          else {
            if(this.checkoutType == 1){
              setTimeout( () => { //stuff gets executed after delay
              this.onInput();
              //generate new cart, budget
              this.selectInput();
              this.produceCart();
              this.produceNewBudget();
              this.adjustClouds();
            }, 1200);
            }
            else{
              setTimeout( () => { //stuff gets executed after delay
              this.onInput();
              //generate new cart, budget
              this.selectInput();
              this.produceCart();
              this.produceNewBudget();
              this.adjustClouds();
            }, 100);
            }
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
        this.co2total = 0;
        for (let i = 0; i < 4; i++){
          this.co2arr[i] = Math.ceil(Math.random() * (this.maxCo2 - this.minCo2) + this.minCo2);
          this.co2total += this.co2arr[i];
        }
        this.totalCompPrice = Math.floor(this.co2price*this.co2total*20)/20;
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
        if(this.testType == 1){
          //this.abc = Math.ceil(Math.random() * 3); //random, without respect to 5,5,5 distribution

          this.abc = this.abc_arr[this.tryNumber];
        }
        else{
          this.abc = 1;
          this.checkoutType = this.cb_arr[this.tryNumber];
        }
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


      updateImage(variantImage) {

        this.productImage = variantImage;
      },
      setImage(variantImage) {
        console.log("in set image")

        this.clickedImage = variantImage;
      },
      disappear() {
        console.log("Hi there is disapper")
        const elem = this.$refs.fourclouds;
        elem.style.transform = 'translateY(5px)'; //align with gun
        elem.style.transform += 'translateX(-100%)';
        elem.style.transform += 'scale(0)';
        this.rotateTornado();
      },

      rotateTornado() {
        const elem = this.$refs.tornado;
        elem.style.transform += 'rotate(360deg)';
      },

      reappear() {
        console.log("Hi there is reappear")
        const elem = this.$refs.fourclouds;
        elem.style.transform = 'translateY(-5px)'; //align with gun
        elem.style.transform += 'translateX(0%)';
        elem.style.transform += 'scale(100%)';
      },



      setClickedImage() {
        console.log("set clicked image")
        this.productImage = this.clickedImage;
      },

      adjustClouds() {
          this.transportSize = 200*(this.co2arr[0]/this.co2total);
          this.materialSize = 200*(this.co2arr[1]/this.co2total);
          this.productionSize = 200*(this.co2arr[2]/this.co2total);
          this.endoflifeSize = 200*(this.co2arr[3]/this.co2total);
      },


      generateInputTypeArray(){
        for (let i = 0; i < (this.cb_arr.length/2); i++) {
          let rand1 = Math.round(Math.random()); // 0 or 1
          let rand2 = 0;

          if(rand1 == 0){
            rand2 = 1;
          }

          this.cb_arr[2*i] = rand1;
          this.cb_arr[2*i+1] = rand2;
        }
      },

    },

    mounted: function() {
      this.produceCart();
      this.produceNewBudget();

      if(this.testType == 1){
        this.generateInputArray();
      }
      else if(this.testType == 0){
        this.generateInputTypeArray();
      }

      this.selectInput();

      this.taskTimeStart = new Date().getTime();

      this.adjustClouds();
    },
}

  </script>


  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

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
    height: 30px;
  }

  .slider-component .slidecontainer .slider {
    -webkit-appearance: none;
    appearance: none;
    height: 4px;
    width: 90%;
    border-radius: 2px;
    background: #c2c2c2;
    outline: none;
    opacity: 0.7;
    -webkit-transition: .2s;
    transition: opacity .2s;
    margin-top: 20px;
    margin-left: 20px;
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
    height: 300px;
  }

  .imagecontainer .CloudImage {
    display: flex;
    justify-content: left;
    align-items: center;
    height: 300px;
    transition: transform 1s;
  }



    .product_image{
      width: 100%
    }
    .slider_stuff{
      display: flex;
    }
    .totals{
      bottom: 0;

    }
    .animation{
      width: 100%;
      display: flex
    }
    .character{
      float: left;
      width: 20%;
      overflow: hidden;
      height: 300px;
      border: 1px;

    }
    .wind{
      float: left;
      width: 20%;
      display: block;
      overflow: hidden;
      height: 300px;
      border: 1px;
    }
    .clouds{
      float: left;
      width: 60%;
      overflow: hidden;
      height: 300px;
      border: 1px;
    }
    .slider{
      width: 70%;
      float: left;
      height: 70px;
      border: 1px;
      display: block;
      margin-bottom: 50px;

    }
    .summary{
      width: 30%;
      float: left;
      height: 70px;
      border: 1px;
      display: block;
      margin-bottom: 50px;
    }

    .buster{
      width: 50%;
      float: right;
      margin-right:50px
    }

    .checkbox{
      width: 50%;
      float: right;
      margin-right:50px
    }

    .bottomtotal{
      font-family: Tahoma, Arial;
      font-size: 1em;
      position: relative;
      height: 4em;
    }

    .products{
      margin-left: 50px;
      display: block;
      width: 15%
    }
    .product_title{
      width: 100%;
      display: flex;
    }
    .header{
      width: 100%;
      height: 300px;
      display: flex;
    }
    .centered{
      display: block;
      margin-left: auto;
      margin-right: auto;
      overflow: hidden;

    }

  .price {
    text-align: right;
  }
  .cloud{
    float: right;
    width: 33.33%;
    display: block
  }
  .confirm{
    margin-top: 5px;
    bottom: 0;

  }
  p {
    text-align: center
  }
  h1 {

  }
  img {
    display: block

  }
  h3 {
    margin: 40px 0 0;
    text-align: center;
    display: block;
  }
  ul {
    list-style-type: none;
    padding: 0;
    text-align: left;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }





  .product {
    /* display: flex; */
    margin: 0 0 30px;
  }

  .product .gemuse {
    position: relative;
  }
  
  .product .boy {
    position: absolute;
    left: 32px;
    top: 4px;
    height: 230px;
  }

  .product .image {
    width: 50%;
    margin: 0 50px 0 0;
  }
  
  .product h1 {
    margin: 0 0 15px;
  }
  
  .product .stockInfo span {
    color: #fff;
    padding: 5px;
    display: inline-block;
    vertical-align: top;
  }
  
  .product .green {
    background: #76bb76;
  }
  
  .product .amber {
    background: #fdc660;
  }
  
  .product .red {
    background: #f54d4d;
  }
  
  .product .stockInfo {
    margin: 0 0 40px;
  }
  
  .product .features {
    margin: 0 0 40px 17px;
  }
  
  .product .features li {
    margin: 0 0 10px;
  }
  
  .product .variants {
    margin: 0 0 5px;
  }
  
  .headshot {
    width: 40px;
    height: auto;
    padding: 3px;
    display: inline-block;
  }





  .transportation{
    height: 150px;
  }
  .materials{
    height: 150px;
  }
  .production{
    height: 150px;
  }
  .endoflife{
    height: 150px;
  }

  /*copied from from https://makitweb.com/html-how-to-show-text-above-image-on-hover/ and adjusted for our purposes*/
  /* Parent Container */
  .content_img{
  position: relative;
  display: flex;
  /* width:  30%; */
  height:50%;
  width:50%;
  /* height: 200px; */
  float: left;
  padding-left: inherit;
  padding-right: inherit;
  padding-top: 5%;
  padding-bottom: 2%;
  /*background-color: #AFDDFF;*/
  justify-content: center;

  ;
  /* margin-right: 10px; */
  }


  /* Child Text Container */
  .content_img div{
  position: absolute;
  bottom: 0;
  right: 0;
  background: transparent;
  color: white;
  margin-bottom: 5px;
  font-family: sans-serif;
  opacity: 0;
  visibility: hidden;
  /* -webkit-transition: visibility 0s, opacity 0.5s linear; */
  transition: visibility 0s, opacity 0.5s linear;
  }

  /* Hover on Parent Container */
  .content_img:hover{
  cursor: help;
  font-size: 8pt;
  }

  .content_img:hover div{
  position: 0 0;
  padding: 2% 20px;
  margin: 2% 2%;
  border-radius: 5px;
  visibility: visible;
  opacity: 1;
  background-color: white;
  color: black;
  }

  .fourclouds{
    width: 100%;
    height: 100%;
    transition: transform 1s;
  }

  </style>
