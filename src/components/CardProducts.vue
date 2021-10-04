<template>
  <div class="card-product">
    <div class="img-card-product" @mouseenter="mouseEnter" @mouseleave="mouseLeave()" :class="{display_icon:condition}">
      <img :src="image" :alt="title">
      <div v-if="condition">
        <div class="icon-product">
          <template v-for="(item, indeks) in icon" :key="indeks">
            <span v-html="item"></span>
          </template>
        </div>
      </div>
    </div>
    <div class="information-card-product">
      <div class="title-card-product">
        <h2>{{title}}</h2>
      </div>
      <div class="rating-product">
        <p v-html="rating"></p>
      </div>
      <div class="price-product">
        <h4>${{price}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props:{
      'image':{
        type:String,
        require:true
      },
      'title':{
        type:String,
        require:true
      },
      'rating':{
        type:Array,
        default: () => []
      },
      'icon':{
        type:Array,
        default: () => []
      },
      'price':{
        type:Number,
        default:0
      },
      'condition':{
        type:Boolean,
        default:false
      }
    },
    setup(props, context){

      const mouseEnter = () => {
        if (props.condition === false){
          context.emit("result_icon", !props.condition);
        }
      }

      const mouseLeave = () => {
        if (props.condition === true){
          context.emit("none_icon", !props.condition);
        }
      }

      return {mouseEnter, mouseLeave}
    }
  }
</script>

<style media="screen">

  .product-list{
    margin-top: 10em;
    padding: 0.5em;
  }

  .title-product{
    display: flex;
    justify-content: center;
    margin-bottom: 55px;
    position: relative;
  }

  .title-product::after{
    content:"";
    width: 100px;
    height: 3px;
    background-color: var(--color-fourth);
    position: absolute;
    bottom: 0;
    top: 40px;
  }

  .title-product h2{
    font-size: 2rem;
    letter-spacing: 1.5px;
    font-weight: var(--font-weight-600);
    color: var(--color-fifth);
  }

  .content-product{
    display: flex;
    justify-content: space-around;
  }

  .card-product{
    width: 20%;
    transition: 0.5s;
  }

  .card-product:hover{
    transform: translateY(15px);
  }
  .img-card-product{
    width: 100%;
    border-radius: 10px;
    position: relative;
  }

  .img-card-product.display_icon::before{
    content: "hello";
    background-color: black;
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    opacity: 0.2;
  }

  .img-card-product img{
    width: 100%;
    height: 300px;
    object-fit: cover;
  }

  .information-card-product{
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px 0;
    box-shadow: 3px 5px 10px rgba(0,0,0,0.75);
  }

  .title-card-product h2{
    font-size: 1.45rem;
    font-weight: var(--font-weight-600);
    color: var(--color-fifth);
  }

  .icon-product{
    position: absolute;
    top: 5em;
    right: 10px;
    display: flex;
    flex-direction: column;
    padding: 10px;
    z-index: 1;
    cursor: pointer;
  }

  .icon-product span{
    margin-top: 10px;
    border-radius: 100%;
    padding: 5px 10px;
    color: white;
    transition: 0.5s;
  }

  .icon-product span:hover{
    background-color: var(--color-fourth);
  }

  .rating-product{
    display: flex;
  }
  .rating-product .fa-star{
    color: var(--color-third);
    font-size: 0.8rem;
  }

  .price-product h4{
    font-size: 1.2rem;
    font-weight: var(--font-weight-500);
    color: var(--color-fourth);
  }
</style>
