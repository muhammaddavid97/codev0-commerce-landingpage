<template>
  <navbar></navbar>
  <banner></banner>
</template>

<script>
  import Banner from "./header/Banner.vue";
  import Navbar from "./header/Navbar.vue";

  export default{
    name:'Header',
    components:{
      'banner':Banner,
      'navbar':Navbar
    }
  }
</script>
