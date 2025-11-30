<script setup lang="ts">
import { onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import logo from './assets/logo.svg'
import Hero from './components/Hero.vue'
import Problem from './components/Problem.vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const problemSection = document.getElementById('problem')

  if (!problemSection) return

  // Set initial state
  gsap.set(problemSection, {
    width: '32px',
    height: '32px',
    left: 0,
    top: '50%',
    x: '-50%',
    y: 0,
    filter: 'grayscale(1) contrast(0)',
    clipPath: 'circle()',
  })

  // Create smooth scroll-based animation with GSAP ScrollTrigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: 'top top',
      end: 'bottom bottom',
      scrub: 1,
      onEnter: () => {
        gsap.to(problemSection, {
          width: '100vw',
          height: '100vh',
          left: 0,
          top: 0,
          x: '0%',
          y: 0,
          filter: 'grayscale(0) contrast(1)',
          clipPath: 'circle(100%)',
          duration: 1.2,
          ease: 'power2.inOut',
        })
      },
      onLeaveBack: () => {
        gsap.to(problemSection, {
          width: '32px',
          height: '32px',
          left: 0,
          top: '50%',
          x: '-50%',
          y: 0,
          filter: 'grayscale(1) contrast(0)',
          clipPath: 'circle()',
          duration: 1.2,
          ease: 'power2.inOut',
        })
      },
    },
  })
})
</script>

<template>
  <div class="scroll"></div>
  <div class="app">
    <img :src="logo" alt="logo" class="logo" />
    <Hero />
    <div class="dots">
      <Problem />
    </div>
  </div>
</template>

<style scoped>
.scroll {
  height: 200vh;
}

.app {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;

  .logo {
    position: fixed;
    top: 1vh;
    left: 3vw;
    z-index: 10;
  }

}
</style>
