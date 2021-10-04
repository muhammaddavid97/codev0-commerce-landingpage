<template id="">
  <banner-component :image="imgBanner" :title_img="imgTitle"></banner-component>
</template>

<script>
  import BannerComponent from "@/components/BannerComponent.vue";
  import {ref} from "vue";

  export default{
    setup(){

      const imgBanner = require("@/assets/img/banner.png");
      const imgTitle = ref("Gambar Banner");

      return {imgBanner, imgTitle}
    },

    components:{
      'banner-component':BannerComponent
    }
  }

</script>
