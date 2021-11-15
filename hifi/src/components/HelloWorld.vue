
<template>

  <div class="hello">
    <p id="insert"></p>
    <h1>{{ msg }}</h1>
    <p>
      Final Confirmation on Selection

    </p>
    <h3>Check Out Summary</h3>

    <div class="cloud">
<ul>
<li>
<div class="cloud2">
    <p>
     CO2 Cloud Information
    </p>

</div>

  </li>
<li>
<div class="cloud2">
<router-link to="/thanks" tag="button">Click to Confirm</router-link>
</div>


</li>
</ul>

    </div>
    <ul>
      <img src="../assets/image.jpg" width="500" height="400">
      <li><p>
      <b>
      Lenovo Laptop
      </b>
      </p>

      <p id="price1"></p>
      <p id="comp1"></p>


      </li>
      <img src="../assets/charger.jpg" width="500" height="400">
      <li><p><b>
      Lenovo Charger
      </b>
      </p>
      <div class="price">
      <p id = "price2">

      </p>
      <p id="price3">
      Price: ${{randomNumber()}}
      </p>
      <p id="demo">Total CO2 Emission: 10kg</p>
      </div>
      </li>
      <img src="../assets/mice.jpg">
      <li><p><b>
      Lenovo Mice + Keyboard
      </b>
      </p>
      <div class="price">
      <p id="price3">
      Price: ${{randomNumber()}}
      </p>
      <p id="demo">Total CO2 Emission: 10kg</p>
      </div>

      </li>

    </ul>
<p>
Total Cost: ${{randomNumber()}}
Total CO2 Emission:
</p>
  </div>
</template>

<script>

export default {

  name: 'HelloWorld',
  props: {
    msg: String,

  },
  mounted(){
    var x=this.randomNumber();
    var y=this.randomNumber();
    var z=this.randomNumber();
    var a=this.randomNumber();
    var b=this.randomNumber();
    var c=this.randomNumber();
    document.getElementById("price1").innerHTML = "Price: $" +x + " |  CO2 Emission: "+a +"kg"
    document.getElementById("price2").innerHTML = "Price: $" +y + " |  CO2 Emission: "+b +"kg"
    document.getElementById("price3").innerHTML = "Price: $" +z + " |  CO2 Emission: "+c +"kg"

  },
methods:
  {
    randomNumber: function(){
    return Math.floor(Math.random()*(10-1+1))+1;
                            }

}
  }


</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p {
  text-align: center
}

.b {
  border: 10px solid red;
  outline: 2px dashed blue;
}
.price {
  text-align: right;
}
.cloud{
  float: right;
  width: 33.33%;
  display: block



}
.cloud2{

  border: 10px solid red;
  outline: 2px dashed blue;
  display: block
}

h1 {

}
img {
  display: block
}
h3 {
  margin: 40px 0 0;
  text-align: left;
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
</style>
