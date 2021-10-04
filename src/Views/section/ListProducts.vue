<template>
    <section class="product-list">
      <div class="title-product">
        <h2>List Products</h2>
      </div>
      <div class="content-product">
        <template v-for="item in products" :key="item.id">
          <cards-products
            :title="item.title_product"
            :image="item.image_product"
            :icon="item.icon_products"
            :rating="item.rating_product"
            :price="item.price_product"
            :condition="item.condition"
            @result_icon="item.condition = $event"
            @none_icon="item.condition = $event"
          ></cards-products>
        </template>
      </div>
    </section>
</template>

<script>
  import CardsProducts from "@/components/CardProducts.vue";
  import produk from "@/mock/products.json";
  import {reactive} from "vue";
  export default {
    setup(){
      const products = reactive(produk);
      return {products}
    },
    components:{
      'CardsProducts':CardsProducts
    }
  }
</script>

<style media="screen">
@media (min-width: 450px) and (max-width: 650px){
  .product-list{
    padding: 15px 0;
  }

  .content-product{
    flex-direction: column;
    align-items: center;
  }

  .card-product{
    width: 50%;
    margin-top: 20px;
  }
}
</style>
