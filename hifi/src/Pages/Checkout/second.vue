<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      End

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
<a href="http://programminghead.com">
<button>
    <p>
     Click to Confirm
    </p>
</button>
</a>
</div>


</li>
</ul>

    </div>



<p>
Total Cost: $24.99
</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
