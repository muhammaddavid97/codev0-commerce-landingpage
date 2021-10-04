<template>
  <div class="card-advert" :class="[card.background, {bounce:card.kondisi}]" @mouseenter="mouseEnter()" @mouseleave="mouseLeave()">
    <div class="card-img-advert">
      <img :src="card.img" alt="gambar product">
    </div>
    <div class="card-title-advert">
      <h3 v-html="card.title"></h3>
      <h4>{{card.brands}}</h4>
    </div>
  </div>
</template>

<script>
  export default {
    props:{
      'card':{
        type:Object,
        default: () => {}
      }
    },
    setup(props, context){

      const mouseEnter = function(){
        if (props.card.kondisi === false){
          context.emit("bouncing", !props.card.kondisi);
        }
      }

      const mouseLeave = function(){
        if (props.card.kondisi === true){
          context.emit("no_bouncing", !props.card.kondisi);
        }
      }

      return {mouseEnter, mouseLeave}
    }
  }
</script>

<style media="screen">
  .cards-clothing{
    width: 100%;
    padding: 10px 20px;
    margin-top: 5em;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .card-advert{
    width: 30%;
    height: 250px;
    overflow: hidden;
    position: relative;
    display: flex;
    border-radius: 10px;
    transition: 1s;
  }

  .card-advert::before{
    content:"";
    border: 2px dashed white;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    z-index: 1;
    margin: 0.8em;
    border-radius: 10px;
  }

  .card-advert.bounce{
    transform: translateY(-10px);
  }

  .card-advert.one{
    background-color: pink;
  }

  .card-advert.two{
    background-color: var(--color-first);
  }

  .card-advert.three{
    background-color: orange;
  }

  .card-img-advert{
    /* width: 200px; */
    padding: 10px 15px;
    height: 350px;
  }

  .card-img-advert img{
    width: 360px;
    height: 250px;
    object-fit: cover;
    position: absolute;
    left: -75px;
    top: 0;
  }

  .card-title-advert{
    position: absolute;
    right: 35px;
    top: 75px;
  }

  .card-title-advert h3{
    font-size: 2rem;
    line-height: 35px;
    color: white;
    font-weight: var(--font-weight-600);
  }

  .card-title-advert h4{
    font-size: 1rem;
    margin-top: 15px;
    color: white;
    font-weight: var(--font-weight-600);
  }

  @media (min-width: 450px) and (max-width:650px){
    .cards-clothing{
      flex-direction: column;
    }

    .card-advert{
      width: 85%;
      margin: 15px 0;
    }

    .card-img-advert img{
      width: 100%;
    }
  }
</style>
