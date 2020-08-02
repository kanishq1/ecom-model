<template>
 <div>
   <Header />
   <Footer />
 </div>  
</template>
<script>
import Header from "./layout/Header";
import Footer from "./layout/Footer";
export default {
  name:"HelloWorld",
  components:{
    Header,
    Footer
  }
  
}
</script>
<style scoped>
</style>