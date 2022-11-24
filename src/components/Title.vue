<template>
  <transition  
      appear
      @before-enter="beforEnter"
      @enter="enter"
      @after-enter="afterEnter"
      >
      <h1 style="font-weight: 900; font-size:  40px;">{{title}}</h1>
    </transition>
</template>

<script>
import gsap from 'gsap';
export default {
    name:"Title",
    props:{
        title:String
    },
    setup(){
        const beforEnter = (el) =>{
      console.log("Befor Enter - transition")
      el.style.transform = 'translateY(-50px)'
      el.style.opacity = 0
    }
    const enter = (el , done) =>{
      console.log("Enter into - gsap")
      gsap.to(el , {
        y: 0,
        opacity: 1,
        duration: 1,
        ease: "bounce.out",
        onComplete: done, //tell After-enter to wait for duration
      })
    }
    const afterEnter = (el) =>{
      console.log("After enter");
    }
        return { beforEnter , enter , afterEnter}
    }
}
</script>