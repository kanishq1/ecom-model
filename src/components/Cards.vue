<template>
  <div> 
      <div class="heading">
          <div class="cover">
              <h1 class="head">Choose from our wide range of products</h1>
          </div>
     </div> 
     
     <div class="sections"> 
       <div class="row">
         <h1>Books</h1>
          <div class="search">
       <form @submit="Submit">
         <select  v-model='product_type' class="searchbar">
         <option value="1">Harry Potter Part1</option>
         <option value="2">Harry Potter Part2</option>
         <option value="3">Harry Potter Part3</option>
         <option value="4">Harry Potter Part4</option>
         </select>
         <button class="btn" type="submit" @click="searchProduct">Search</button>
       </form>
        </div>
       </div> 
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
    props:['products'] ,
    data(){
      return{
        product_type:""
      }
    },
    methods:{
      Submit(e){
        e.preventDefault();
        console.log("Testing...");
      },
      searchProduct(){
        console.log(this.product_type);
        const searchResult=this.product_type;
        this.$emit('search-it',searchResult);     
        this.product_type="";   
      }
    }  
    
}
</script>
<style scoped>
 * {
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.column {
  float: left;
  width: 25%;
  padding: 0 10px;
}

.row {margin: 10 -5px;}

.row:after {
  content: "";
  display: table;
  clear: both;
}

@media screen and (max-width: 600px) {
  .column {
    width: 100%;
    display: block;
    margin-bottom: 20px;
  }
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: 16px;
  text-align: center;
  background-color: rgb(255, 251, 251);
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
.card:hover{
    box-shadow:0 8px 20px 0 rgba(0,0,0,0.7);
}

.searchbar{
  padding:10px 30px;

}
.btn{
  padding:10px 30px;

}
</style>