
 <template>
  <div id="app">
    <div class="content_img">
      <div class="type"></div>
      <!-- <h3>Transportation</h3> -->
        <img src="./assets/cloud_transportation.png" width='100%' align="bottom" alt="CO2 emission through transportation is caused at early stages of your product's life cycle. In particular, raw materials have to be excavated and transported to the location of production. In some cases, production may be split into different locations, leading to even more transportation needed. All of this causes CO2 to be set free. Further, CO2 is emitted during the transportation of the product to your home.">
      <div class="textbox">
        CO2 emission through transportation is caused at early stages of your product's life cycle. In particular, raw materials have to be excavated and transported to the location of production. In some cases, production may be split into different locations, leading to even more transportation needed. All of this causes CO2 to be set free. Further, CO2 is emitted during the transportation of the product to your home.
      </div>
    </div>
    <div class="content_img">
      <div class="type"></div>
      <img src="./assets/cloud_materials.png" width='100%' align="bottom" alt="The production of raw material is linked to CO2 emissions through the process' energy consumption.">
      <div class="textbox">
        The production of raw material is linked to CO2 emissions through the process' energy consumption.
      </div>
    </div>
    <div class="content_img">
      <div class="type"></div>
      <img src="./assets/cloud_production.png" width='100%' align="bottom" alt="The processing of raw materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods.">
      <div class="textbox">
        The processing of raw materials to the final good can be linked with a lot of energy consumption. In addition, other resources, such as water, may be needed during the production process. Thus, CO2 consumption may also be linked to the production of goods.
      </div>
    </div>
    <div class="content_img">
      <div class="type"></div>
      <img src="./assets/cloud_endoflife.png" width='100%' align="bottom" alt="Have you ever thought oc the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.">
      <div class="textbox">
        Have you ever thought oc the recyclability of the products you're buying? If a product has a longer life time and/or can be fully recycled, it is considered to emit less CO2.
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'app',
  data () {
    return {

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
