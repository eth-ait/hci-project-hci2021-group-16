
<template>
<div class="whole">
  <div class="header">
    <img alt="Vue logo" src="../assets/logo.png" class="centered">
  </div>

    <h1>Check Out</h1>
    <p>
      Final Confirmation on Selection
    </p>


    <div class="buster">
      <div class="bustertitle">
        <h1> CO2 Compensation Visualization </h1>
      </div>
        <div class="animation">
          <div class="character"> <p> character_placement </p> </div>
          <div class="wind"> <p> wind_placement </p> </div>
          <div class="clouds"> <p> clouds_placement </p> </div>
        </div>
        <div class= "slider_stuff">
          <div class= "slider">

          </div>
          <div class= "summary">

          </div>
        </div>
        <div class= "totals">
          <div class="confirm">
            <router-link to="/thanks" tag="button">Click to Confirm</router-link>
          </div>

          <div class="bottomtotal">
            <p id="totalprice"></p>
            <p id="totalCO2"></p>
          </div>
          </div>

    </div>

    <div class="products">
      <div class="product_title">
        <h3>Check Out Summary</h3>
      </div>
      <ul>
        <img src="../assets/image.jpg" class="product_image">
      <li>
        <p>Lenovo Laptop</p>
        <p id="price1"></p>
        <p id="comp1"></p>
      </li>
      <img src="../assets/charger.jpg" class="product_image">
      <li>
        <p>Lenovo Charger</p>
        <p id="price2"></p>
        <p id="comp2"></p>
      </li>
      <img src="../assets/mice.jpg" class="product_image">
      <li>
        <p>Lenovo Mice+Keybaord</p>
        <p id="price3"></p>
        <p id="comp3"></p>
      </li>
    </ul>
  </div>
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
    var w = x+y+z
    var d = a+b+c
    document.getElementById("totalprice").innerHTML = "Total Price: $" +w
    document.getElementById("totalCO2").innerHTML = "Total CO2 Emission: "+d +"kg"
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
    background:yellow;

  }
  .wind{
    float: left;
    width: 20%;
    display: block;
    overflow: hidden;
    height: 300px;
    border: 1px;
    background:red;
  }
  .clouds{
    float: left;
    width: 60%;
    overflow: hidden;
    height: 300px;
    border: 1px;
    background:orange;
  }
  .slider{
    width: 70%;
    float: left;
    height: 70px;
    border: 1px;
    background:blue;
    display: block;
    margin-bottom: 50px;

  }
  .summary{
    width: 30%;
    float: left;
    height: 70px;
    border: 1px;
    background:green;
    display: block;
    margin-bottom: 50px;
  }

  .buster{
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
  .whole{
    diplay: flex
  }
  .products{
    margin-left: 50px;
    display: block;
    width: 40%
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
  margin-top: 50px;
  border: 10px solid red;
  outline: 2px dashed blue;
  postion: absolute;
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
</style>
