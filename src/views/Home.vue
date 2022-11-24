<template>
  <div class="home">
    <Title title="Todo List" />
    <transition name="fade">
      <Toast v-if="showToast" />
    </transition>
    <Todos @badValue="triggerToast" />

  </div>
</template>

<script>
import { ref } from 'vue'
import Toast from '../components/Toast.vue'
import Todos from '../components/Todos.vue'
import Title from '../components/Title.vue'

export default {
  components: { Toast, Todos , Title },
  setup() {
    const showToast = ref(false)

    const triggerToast = () => {
      showToast.value = true;
      setTimeout(() => showToast.value = false, 1800)
    }

    return { showToast, triggerToast }
  }
}
</script>

<style>
/* .fade-enter-from{
  opacity: 0;
  transform: translateY(-60px);
}
.fade-enter-to{
  opacity: 1;
  transition: translateY(0);
} */
.fade-enter-active{
  /* transition: all 0.3s ease; */
  animation: shake 1s ease;
}
/* Its default values so Does not matter */
/* .fade-leave-from{ 
  opacity: 1;
  transform: translateX(0);
} */
.fade-leave-to{
  opacity: 0;
  transform: translateY(-60px);
}
.fade-leave-active{
  transition: all 0.3s ease;
}


@keyframes shake {
  0% {transform: translateY(-60px); opacity: 0;}
  50% {transform: translateY(0px); opacity: 1;}
  60% {transform: translateX(-8px);}
  70% {transform: translateX(8px);}
  80% {transform: translateX(-6px);}
  90% {transform: translateX(6px);}
  100% {transform: translateX(0px);}
}
</style>