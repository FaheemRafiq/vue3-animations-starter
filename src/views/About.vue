<template>
  <div class="about">
    <Title title="About"/>
    <transition-group 
      tag="div" 
      appear 
      name="text"
      >
      <p :key="1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
      <p :key="2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
      <p :key="3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    </transition-group>
  </div>
</template>

<script>
import Title from '../components/Title.vue'
export default {
  components:{Title},
  setup() {
  }
}
</script>

<style>
  .about {
    max-width: 600px;
    margin: 20px auto;
  }

  /* Text transition */
  .text-enter-from{
    opacity: 0;
    transform: translateY(50px);
  }
  .text-enter-active{
    transition: all 0.8s ease;
  }

</style>