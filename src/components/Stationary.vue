<template>
  <div>     
     <div class="sections">
         <h1>Accessories</h1>
        <div class="search">
           <form @submit="Submit">
              <select  v-model='product_type' class="searchbar">
              <option value="1">Pens</option>
              <option value="2">Notebook</option>
              <option value="3">Brushpens</option>
              <option value="4">Origami Paper</option>
             </select>
                 <button class="btn" type="submit" @click="searchAccessory">Search</button>
           </form>
         </div>
     </div>
    <div class="row">
        <div class="column" v-for="stationary in stationaries" v-bind:key="stationary.id">
            <div class="card">
                <h1>{{stationary.item}}</h1>
                <h2>{{stationary.rate}}</h2>
            </div>
        </div>
    </div>  
  </div>    
</template>
<script>
export default {
    name:"Stationary",
    props:['stationaries'],
    data(){
      return{
        product_type:""
      }
    },
    methods:{
      Submit(e){
        e.preventDefault();
        console.log("Testing..");
      },
      searchAccessory(){
        const acc=this.product_type;
        this.$emit('search-up',acc);
        this.product_type="";


      }

    }
    
}
</script>
<style scoped>
* {
  box-sizing: border-box;
}

.searchbar{
  padding:10px 30px;

}
.btn{
  padding:10px 30px;

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
  background-color: rgb(255, 250, 250);
}

.sections{
    text-align: left;
    margin:20px;
}
.card:hover{
    box-shadow:0 8px 20px 0 rgba(0,0,0,0.7);
}
</style>