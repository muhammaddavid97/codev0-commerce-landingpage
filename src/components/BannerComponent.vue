<template>
  <div class="banner-component">
    <div class="title-banner">
      <div class="title-top">
        <h2><span>70%</span> SALE OFF</h2>
      </div>
      <div class="title-bottom">
        <h1>Summer Vibes mode on</h1>
      </div>
      <div class="btn-banner">
        <button type="button" name="button">SHOP NOW</button>
      </div>
    </div>
    <div class="img-banner">
      <img :src="image" :alt="title_img">
    </div>
  </div>
</template>

<script>
  export default{
    props:{
      'image':{
        type:String,
        required:true
      },
      'title_img':{
        type:String,
        required:true
      }
    }
  }

</script>

<style>

  .banner-component{
    width: 100%;
    background-color: var(--color-first);
    min-height: 100vh;
    display: flex;
    justify-content: space-between;
    position: relative;
    overflow: hidden;
  }

  .title-banner{
    min-width: 30%;
    height: 250px;
    transform: translate(20%, 70%);
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .title-banner .title-top h2{
    font-size: 1.6rem;
    color: var(--color-fifth)
  }

  .title-banner .title-top h2 span{
    color: var(--color-third);
  }

  .title-banner .title-bottom h1{
    font-size: 3.3rem;
    line-height: 0.8em;
    color: var(--color-fifth);
  }

  .img-banner{
    position:relative;
    top: 50px;
    right: 50px;
  }

  .btn-banner{
    margin-top: 1.5em;
    display: flex;
  }

  .btn-banner button{
    padding: 15px 30px;
    font-size: 1rem;
    font-weight: var(--font-weight-600);
    color: white;
    border: none;
    cursor: pointer;
    background-color: var(--color-fourth);
  }

  @media (min-width: 450px) and (max-width: 650px){
    .banner-component{
      flex-direction: column;
    }

    .title-banner{
      transform: translate(15%, 30%);
    }

    .title-banner .title-bottom{
      width: 80%;
    }

    .title-banner .title-top h1{
      font-size: 1.4em;
    }
    .title-banner .title-bottom h1{
        font-size: 2.5em;
    }
    .img-banner img{
      height: 15em;
    }

    .img-banner{
      top: 60px;
      left: 0;
      right: 0;
    }
  }
</style>
