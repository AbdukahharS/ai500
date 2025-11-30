<script setup lang="ts">
import { onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import logo from './assets/logo.svg'
import Hero from './components/Hero.vue'
import Problem from './components/Problem.vue'
import Solution from './components/Solution.vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const problemSection = document.getElementById('problem')
  const solutionSection = document.getElementById('solution')

  if (!problemSection || !solutionSection) return

  // Set initial state
  gsap.set(problemSection, {
    width: '32px',
    height: '32px',
    left: 0,
    top: '50%',
    x: '-50%',
    y: 0,
    filter: 'grayscale(1) contrast(0)',
    clipPath: 'circle(32px)',
    borderRadius: '50%',
  })
  gsap.set(solutionSection, {
    width: '32px',
    height: '32px',
    left: 0,
    top: '50%',
    x: '-50%',
    y: 44,
    filter: 'grayscale(1) contrast(0)',
    clipPath: 'circle(32px)',
    borderRadius: '50%',
  })

  // Problem section scroll trigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: 'top top',
      end: '33% top',
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
          borderRadius: '0%',
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
          clipPath: 'circle(32px)',
          duration: 1.2,
          ease: 'power2.inOut',
          borderRadius: '50%',
        })
      },
    },
  })

  // Solution section scroll trigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: '50% top',
      end: '66% top',
      scrub: 1,
      onEnter: () => {
        gsap.to(solutionSection, {
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
          borderRadius: '0%',
        })
      },
      onLeaveBack: () => {
        gsap.to(solutionSection, {
          width: '32px',
          height: '32px',
          left: 0,
          top: '50%',
          x: '-50%',
          y: 44,
          filter: 'grayscale(1) contrast(0)',
          clipPath: 'circle(32px)',
          duration: 1.2,
          ease: 'power2.inOut',
          borderRadius: '50%',
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
      <Solution />
    </div>
  </div>
</template>

<style scoped>
.scroll {
  height: 300vh;
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
    z-index: 100;
  }

}
</style>
