
<template>
 <div id="app">
   <div class="content_img">
     <div class="type"></div>
     <!-- <h3>Transportation</h3> -->
       <img class="transportation" src="./assets/cloud_transportation.png" :style='cssVars' alt="CO2 emission through transportation is caused at early stages of your product's life cycle. In particular, raw materials have to be excavated and transported to the location of production. In some cases, production may be split into different locations, leading to even more transportation needed. All of this causes CO2 to be set free. Further, CO2 is emitted during the transportation of the product to your home.">
     <div class="textbox">
      CO2 emission through transportation is caused at early stages of your product's life cycle. In particular, raw materials have to be excavated and transported to the location of production. In some cases, production may be split into different locations, leading to even more transportation needed. All of this causes CO2 to be set free. Further, CO2 is emitted during the transportation of the product to your home. The transport of you purchase will emit {{emissionvalues[0]}}KG CO2.
     </div>
   </div>
   <div class="content_img">
     <div class="type"></div>
     <img class="materials" src="./assets/cloud_materials.png" :style='cssVars' alt="The production of raw material is linked to CO2 emissions through the process' energy consumption.">
     <div class="textbox">
        The production of raw material is linked to CO2 emissions through the process' energy consumption. The materials of you purchase will contribute to {{emissionvalues[1]}}KG of CO2 emisisons.
     </div>
   </div>
   <div class="content_img">
     <div class="type"></div>
     <img class="production" src="./assets/cloud_production.png" :style='cssVars' align="bottom" alt="The processing of raw materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods.">
     <div class="textbox">
       The processing of raw materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods. The production of you purchased goods emits {{emissionvalues[2]}}KG CO2.
     </div>
   </div>
   <div class="content_img">
     <div class="type"></div>
     <img class= "endoflife" src="./assets/cloud_endoflife.png" :style='cssVars' alt="Have you ever thought oc the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.">
     <div class="textbox">
       Have you ever thought oc the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.  The end of life property of your goods contributes to {{emissionvalues[3]}}KG of CO2 emissions.
     </div>
   </div>
 </div>

</template>

<script>
export default {
 name: 'app',
 props: {
//   emissiontrans: {
//   type: Number,
//   default: 120
// },
//   emissionmat: {
//   type: Number,
//   default: 50
// },
//   emissionprod: {
//   type: Number,
//   default: 80
// },
//   emissioneol: {
//   type: Number,
//   default: 100
// },
  emissionvalues:{
    type: Array,
    default:[110, 70, 100, 120] /*emissions [trans mat prod eol]*/
},
 },
 data () {
   return {
     trans: this.emissionvalues[0],
     mat: this.emissionvalues[1],
     prod: this.emissionvalues[2],
     eol: this.emissionvalues[3],
   };
 },
 computed: {
   // test:function(a){
   //   console.log('test');
   //   var total=this.emissiontrans+this.emissionmat+this.emissionprod+this.emissioneol;
   //   return a/total;
   // },
    cssVars() {
      return {
        // '--emissiontrans': this.emissiontrans+'%',
        // '--emissionmat': this.emissionmat+'%',
        // '--emissionprod': this.emissionprod+'%',
        // '--emissioneol': this.emissioneol+'%',
        '--emissiontrans': this.emissionvalues[0]+'%',
        '--emissionmat': this.emissionvalues[1]+'%',
        '--emissionprod': this.emissionvalues[2]+'%',
        '--emissioneol': this.emissionvalues[3]+'%',

      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: red;
  /* margin-top: 60px;
  margin-left: 22%; */
  height: 300px;
  font-size: 10px;
  background-color: #AFDDFF;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.post img {
  background: transparent;
}


.transportation{
  height: var(--emissiontrans);
  align: bottom;
}
.materials{
  height: var(--emissionmat);
  align: bottom;
}
.production{
  height: var(--emissionprod);
  align: bottom;
}
.endoflife{
  height: var(--emissioneol);
  align: bottom;
}

/*copied from from https://makitweb.com/html-how-to-show-text-above-image-on-hover/ and adjusted for our purposes*/
/* Parent Container */
.content_img{
 position: relative;
 display: flex;
 /* width:  30%; */
 height:200px;
 /* height: 200px; */
 float: left;
 padding-left: inherit;
 padding-right: inherit;
 padding-top: 5%;
 padding-bottom: 2%;
 background-color: #AFDDFF;

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

/*copied from https://projects.verou.me/bubbly/ */
/* .textbox {
	position: relative;
	background: #ffffff;
	border-radius: .4em;
  width: 80%;
}

.textbox:after {
	content: '';
	position: absolute;
	left: 0;
	top: 50%;
	width: 0;
	height: 0;
	border: 51px solid transparent;
	border-right-color: #ffffff;
	border-left: 0;
	margin-top: -51px;
	margin-left: -51px;
} */
</style>
