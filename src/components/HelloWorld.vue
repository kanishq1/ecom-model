<template>
 <div>
   <Cards v-bind:products="products" v-on:search-it="SearchResults" />
   <Stationary v-bind:stationaries="stationaries" v-on:search-up="searchAcc" />
   <Footer />
 </div>  
</template>
<script>
import Cards from "./Cards";
import Stationary from "./Stationary";
import Footer from "./layout/Footer";
export default {
  name:"HelloWorld",
  components:{
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
          rate:"300/-",
          img:"../assets/ecom.jpg"
        },
        {
          id:2,
          item:"Harry Potter and The Chamber Of Secrets",
          rate:"300/-",
           img:"../assets/ecom.jpg"

        },
        {
          id:3,
          item:"Harry Potter and The Prisoner of Azkaban",
          rate:"250/-",
          img:"../assets/ecom.jpg"

        },
        {
          id:4,
          item:"Harry Potter and The Goblet Of Fire",
          rate:"200/-",
          img:"../assets/ecom.jpg"

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
          rate:"45/-"
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
  },
  methods:{
    SearchResults(searchResult){
      this.products=this.products.filter(product=>product.id==searchResult);
    },
    searchAcc(acc){
      this.stationaries=this.stationaries.filter(stationary=>stationary.id==acc);
    }
  }
  
  
}
</script>
<style scoped>
 
</style>