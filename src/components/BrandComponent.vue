<template>
  <div class="brand-product">
    <img :src="brand.image" :alt="brand.title">
  </div>
</template>

<script>

  export default{
    props:{
      'brand':{
        type:Object,
        default: () => {}
      }
    }
  }

</script>

<style media="screen">
.brand-product{
  width: 150px;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.brand-product img{
  width: 60px;
  height: 60px;
}
</style>
