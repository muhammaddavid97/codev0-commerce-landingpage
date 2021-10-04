<template>
  <nav class="navbar-component" :class="{sticky:isSticky}">
    <div class="logo">
      <h2>Codevo</h2>
    </div>
    <div class="navigation-menu">
      <ul :class="{slide:condition}">
        <li v-for="(item, indeks) in navMenu" :key="indeks">
          <a :href="'#' + item">{{item.title}}</a>
        </li>
        <li>
          <a href="#" v-html="icon_nav"></a>
        </li>
      </ul>
      <div class="menu-toggle" @click="menuHamburger()">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
  </nav>
</template>

<script>
  import {ref, reactive, onUnmounted} from "vue";
  export default{
    setup(){

      const isSticky = ref(false);
      const scrollPosition = ref(0);
      const menu = [
        {link:'home', title:'Home'},
        {link:'products', title:'Products'},
        {link:'about', title:'About'},
        {link:'contact', title:'Contact'},
        {link:'account', title:'Account'}
      ];
      const navMenu = reactive(menu);
      const icon_nav= ref('<i class="fas fa-shopping-bag"></i>');
      const condition = ref(false);
      const handleScroll = () => {
        scrollPosition.value = window.scrollY;
        if (scrollPosition.value > 0){
          isSticky.value = true;
        }else{
          isSticky.value = false;
        }
      }
      const unMountedScroll = function(){
        window.removeEventListener("scroll", handleScroll);
      }

      const menuHamburger = () => {
        condition.value = !condition.value;
      }

      window.addEventListener("scroll", handleScroll);
      onUnmounted(unMountedScroll);

      return {isSticky, scrollPosition, navMenu, icon_nav, handleScroll, menuHamburger, condition}
    }
  }

</script>

<style media="screen">
  .navbar-component{
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    align-items: center;
    z-index: 9999;
    position: fixed;
  }

  .navbar-component.sticky{
    background-color: var(--color-second);
    padding: 1em 0.5em;
    transition: 0.5s;
  }

  .navigation-menu{
    width: 45%;
    text-align: center;
  }

  .navigation-menu ul{
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .navigation-menu ul li{
    list-style: var(--value-none);
  }

  ul li > a{
    text-decoration: var(--value-none);
    font-size: 1rem;
    font-weight: var(--font-weight-500);
    color: white;
  }

  .logo{
    margin-left: 2em;
  }
  .logo h2{
    font-size: 1.5rem;
    font-weight: var(--font-weight-600);
    color: white;

  }

  .menu-toggle{
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-end;
    cursor: pointer;
    display: none;
  }

  .menu-toggle span{
    display: block;
    width: 30px;
    height: 5px;
    background-color: var(--color-fifth);
    margin-top: 5px;
  }

  @media (min-width:450px) and (max-width:650px){
    .navbar-component{
      /* background-color: var(--color-fifth); */
    }

    .navigation-menu{
      width: 100%;
    }

    .menu-toggle{
      display: flex;
    }

    .menu-toggle span{
      background-color: white;
    }

    .navigation-menu ul{
      position: absolute;
      flex-direction: column;
      justify-content: space-around;
      width: 80%;
      min-height: 90vh;
      top: 3.4em;
      left: 0;
      background-color: white;
      transform: translateX(-100%);
      transition: 1s;
    }

    .navigation-menu ul li a{
      color: var(--color-fifth);
    }

    .navigation-menu::before{
      content:"hello";
      position: absolute;
      right: 11rem;;
    }

    .navigation-menu ul.slide{
      transform: translateY(0);
    }
  }
</style>
