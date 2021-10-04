<template>
  <div class="card-commentar">
    <div class="icon-commentar">
      <span v-html="comment.quote"></span>
    </div>
    <div class="text-comment">
      <!-- <p>lorem ipsum dolor it, ammet consectetur adipisicing elit. Debits, fugiat labore, Veritatis et amnis consequatur</p> -->
      <p>{{comment.text}}</p>
    </div>
    <div class="rating-comment">
      <template v-for="(item, indeks) in comment.rating" :key="indeks">
        <span v-html="item"></span>
      </template>
    </div>
    <div class="img-comment">
      <img :src="comment.img" alt="profile">
    </div>
    <div class="name">
      <h4>{{comment.name}}</h4>
    </div>
  </div>
</template>

<script>
  export default{
    props:{
      'comment':{
        type:Object,
        default:() => {}
      }
    }
  }
</script>

<style media="screen">
  .card-commentar{
    width: 25%;
    min-height: 350px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    padding: 0 15px;
    box-shadow: 3px 5px 15px rgba(0,0,0,0.75);
    border-radius: 15px;
    transition: 0.5s;
  }

  .card-commentar:hover{
    transform: translateY(-20px);
  }

  .icon-commentar{
    font-size: 2rem;
    color: var(--color-fourth);
    border: none;
  }

  .text-comment{
    font-size: 1rem;
    font-weight: var(--font-weight-500);
    text-align: center;
  }

  .rating-comment{
    font-size: 0.8rem;
    letter-spacing: 2px;
    color: var(--color-third);
  }

  .img-comment{
    background-color: yellow;
    width: 70px;
    height: 70px;
    border-radius: 100%;
    overflow: hidden;
  }

  .img-comment img{
    width: 70px;
    height: 70px;
    object-fit: cover;
  }

  .name h4{
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--color-second);
  }
</style>
