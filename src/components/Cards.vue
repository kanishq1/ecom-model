<template>
  <div> 
      <div class="heading">
          <div class="cover">
              <h1 class="head">Choose from our wide range of products</h1>
            </div>
     </div> 
     <div class="sections">
         <h1>Books</h1>
     </div>
    <div class="row">
        <div class="column" v-for="product in products" v-bind:key="product.id">
            <div class="card">
                <h1>{{product.item}}</h1>
                <h2>{{product.rate}}</h2>
            </div>
        </div>
    </div>      
  </div>    
</template>
<script>
export default {
    name:"Cards",
    props:['products']   
    
}
</script>
<style scoped>
 * {
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Float four columns side by side */
.column {
  float: left;
  width: 25%;
  padding: 0 10px;
}

/* Remove extra left and right margins, due to padding */
.row {margin: 10 -5px;}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive columns */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
    display: block;
    margin-bottom: 20px;
  }
}

/* Style the counter cards */
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: 16px;
  text-align: center;
  background-color: rgb(241, 241, 241);
}
.heading{
    background-image: url("../assets/wallpaper2.png");
    background-size: contain;    
    margin:100px 0;
    width:100%;
    height:300px;
    color:white;
}
.cover{
    height:300px;
    width:80%;
    margin:0 auto;
    background-color: rgba(0,0,0,0.7);
    text-align: center;
}
.head{
    padding-top:100px;
}
.sections{
    text-align: left;
    margin:20px;
}

</style>