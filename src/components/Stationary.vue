<template>
  <div>     
     <div class="sections">
         <h1>Accessories</h1>
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
    props:['stationaries']
    
}
</script>
<style scoped>
* {
  box-sizing: border-box;
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
  background-color: rgb(241, 241, 241);
}

.sections{
    text-align: left;
    margin:20px;
}
</style>