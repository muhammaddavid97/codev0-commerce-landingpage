<template id="">
  <section class="testimonial">
    <div class="title-testimonial">
      <h2>Testimonial Person Group</h2>
    </div>
    <div class="testimonial-person">
      <commentar-column v-for="comment in comments" :key="comment.id" :comment="comment"></commentar-column>
    </div>
  </section>
</template>

<script>
  import {reactive} from "vue";
  import CommentarColumn from "@/components/CommentarColumn.vue";

  export default {
    setup(){

      const dataCommentar = [
        {
          id:1,
          quote:'<i class="fas fa-quote-right"></i>',
          text:'lorem ipsum dolor it, ammet consectetur adipisicing elit. Debits, fugiat labore, Veritatis et amnis consequatur',
          rating:[
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>'
          ],
          img:require("@/assets/img/profile1.jpg"),
          name:'Ato Waryoto'
        },
        {
          id:2,
          quote:'<i class="fas fa-quote-right"></i>',
          text:'lorem ipsum dolor it, ammet consectetur adipisicing elit. Debits, fugiat labore, Veritatis et amnis consequatur',
          rating:[
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>'
          ],
          img:require("@/assets/img/profile2.jpg"),
          name:'Bambang Markonah'
        },
        {
          id:3,
          quote:'<i class="fas fa-quote-right"></i>',
          text:'lorem ipsum dolor it, ammet consectetur adipisicing elit. Debits, fugiat labore, Veritatis et amnis consequatur',
          rating:[
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>',
            '<i class="fas fa-star"></i>'
          ],
          img:require("@/assets/img/profile3.jpg"),
          name:'Sandaiga Usoy'
        }
      ];

      const comments = reactive(dataCommentar);

      return {comments}
    },

    components:{
      'commentar-column':CommentarColumn
    }
  }

</script>

<style media="screen">

  .testimonial{
    width: 100%;
    min-height: 50vh;
    margin: 10em 0;
    padding: 15px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .title-testimonial{
    display: flex;
    justify-content: center;
    margin-bottom: 5rem;
  }

  .title-testimonial h2{
    font-size: 2rem;
    color: var(--color-second);
    font-weight: var(--font-weight-500);
  }

  .testimonial-person{
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  @media (min-width:450px) and (max-width:650px){
    .testimonial{
      padding: 25px 0;
    }

    .testimonial-person{
      flex-direction: column;
    }

    .card-commentar{
      width: 60%;
      margin-top: 25px;
    }

    .card-commentar:hover{
      transform: translateY(5px);
    }

    .title-testimonial{
      width: 65%;
      justify-content: center;
      text-align: center;
    }
  }
</style>
