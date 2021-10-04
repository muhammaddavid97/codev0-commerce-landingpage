<template>
  <section class="brands">
      <brands v-for="brand in brandProducts" :key="brand.id" :brand="brand"></brands>
  </section>
</template>

<script>

  import {reactive} from "vue";
  import Brands from "@/components/BrandComponent.vue";

  export default{
    setup(){

      const dataBrands = [
        {id:1, title:'Adidas', image:require("@/assets/img/brand1.png")},
        {id:2, title:'Puma', image:require("@/assets/img/brand2.png")},
        {id:3, title:'Adidas', image:require("@/assets/img/brand1.png")},
        {id:4, title:'Puma', image:require("@/assets/img/brand2.png")},
        {id:5, title:'Adidas', image:require("@/assets/img/brand1.png")},
        {id:6, title:'Puma', image:require("@/assets/img/brand2.png")},
      ];

      const brandProducts = reactive(dataBrands);

      return {brandProducts}
    },

    components:{
      'brands':Brands
    }
  }

</script>


<style media="screen">
  .brands{
    display: flex;
    justify-content: space-around;
    position: relative;
    top: 0;
  }

  @media (min-width:450px) and (max-width: 650px){
    .brands{
      align-items: center;
      min-height: 350px;
      margin: -150px auto;
      flex-wrap: wrap;
    }

    .brand-product img{
      width: 100px;
      height: 100px;
    }
  }
</style>
