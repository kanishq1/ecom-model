<template>
 <div>
   <Header />
   <Cards v-bind:products="products" />
   <Stationary v-bind:stationaries="stationaries" />
   <Footer />
 </div>  
</template>
<script>
import Header from "./layout/Header";
import Cards from "./Cards";
import Stationary from "./Stationary";
import Footer from "./layout/Footer";
export default {
  name:"HelloWorld",
  components:{
    Header,
    Footer,
    Cards,
    Stationary
  },
  data(){
    return{
      products:[
        {
          id:1,
          item:"Harry Potter and The Sorceror's Stone",
          rate:"300/-"
        },
        {
          id:2,
          item:"Harry Potter and The Chamber Of Secrets",
          rate:"300/-"
        },
        {
          id:3,
          item:"Harry Potter and The Prisoner of Azkaban",
          rate:"250/-"
        },
        {
          id:4,
          item:"Harry Potter and The Goblet Of Fire",
          rate:"200/-"
        }
      
      ],
      stationaries:[
        {
          id:1,
          item:"Pens",
          rate:"10/-"
        },
        {
          id:2,
          item:"Notebook",
          rate:"45"
        },
        {
          id:3,
          item:"Brushpens",
          rate:"800/-"
        },
        {
          id:4,
          item:"Origami Paper",
          rate:"100/-"
        }
      ]
    }
  }
  
  
}
</script>
<style scoped>
 
</style>