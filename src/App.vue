<template>
  <Header />
  <Main />
  <Footer />
</template>

<script>
  import Header from "@/Views/Header.vue";
  import Main from "@/Views/Main.vue";
  import Footer from "@/Views/Footer.vue";

  export default{
    components:{
      Header,
      Main,
      Footer
    }
  }
</script>
