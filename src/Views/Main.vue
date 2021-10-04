<template>
  <main>
    <clothing></clothing>
    <list-products></list-products>
    <commentar></commentar>
    <brands></brands>
  </main>
</template>

<script>

  import Clothing from "./section/Clothing.vue";
  import ListProducts from "./section/ListProducts.vue";
  import Commentar from "./section/Commentar.vue";
  import Brands from "./section/Brands.vue";

  export default{
    components:{
      'Clothing':Clothing,
      'ListProducts':ListProducts,
      'Commentar':Commentar,
      'Brands':Brands
    }
  }
</script>
