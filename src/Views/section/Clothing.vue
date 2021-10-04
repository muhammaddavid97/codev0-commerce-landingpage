<template>
  <section class="cards-clothing">
    <cards-clothing v-for="card in cardsClothing" :key="card.id" :card="card" @bouncing= "card.kondisi = $event" @no_bouncing = "card.kondisi = $event"></cards-clothing>
  </section>
</template>

<script>
  import CardsClothing from "@/components/CardsClothing.vue";
  import {reactive} from "vue";

  export default{
    setup(){

      const dataCardsClothing = [
        {id:1, title:'Girls<br>Clothing', brands:'World Best Brands', img:require('@/assets/img/advert1.png'), background:'one', kondisi:false},
        {id:2, title:'Summer<br>Clothing', brands:'World Best Brands', img:require('@/assets/img/advert2.png'), background:'two', kondisi:false},
        {id:3, title:'Boys<br>Clothing', brands:'World Best Brands', img:require('@/assets/img/advert3.png'), background:'three', kondisi:false}
      ];
      const cardsClothing = reactive(dataCardsClothing);

      return {cardsClothing}
    },

    components:{
      'cards-clothing':CardsClothing
    }
  }
</script>
