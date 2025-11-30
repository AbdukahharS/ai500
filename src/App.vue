<script setup lang="ts">
import { onMounted, ref } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import logo from './assets/logo.svg'
import Hero from './components/Hero.vue'
import Problem from './components/Problem.vue'
import Solution from './components/Solution.vue'
import Team from './components/Team.vue'
import Roadmap from './components/Roadmap.vue'
import Loading from './components/Loading.vue'

gsap.registerPlugin(ScrollTrigger)

const isLoading = ref(true)
const showLoading = ref(true)

const handleLoadingComplete = () => {
  showLoading.value = false
}

onMounted(() => {
  // Wait for window load event
  window.addEventListener('load', () => {
    setTimeout(() => {
      isLoading.value = false
    }, 500)
  })

  const problemSection = document.getElementById('problem')
  const solutionSection = document.getElementById('solution')
  const teamSection = document.getElementById('team')
  const roadmapSection = document.getElementById('roadmap')

  if (!problemSection || !solutionSection || !teamSection || !roadmapSection) return

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

  gsap.set(teamSection, {
    width: '32px',
    height: '32px',
    left: 0,
    top: '50%',
    x: '-50%',
    y: 88,
    filter: 'grayscale(1) contrast(0)',
    clipPath: 'circle(32px)',
    borderRadius: '50%',
  })

  gsap.set(roadmapSection, {
    width: '32px',
    maxHeight: '32px',
    left: 0,
    top: '50%',
    x: '-50%',
    y: 132,
    filter: 'grayscale(1) contrast(0)',
    clipPath: 'circle(32px)',
    borderRadius: '50%',
  })

  // Problem section scroll trigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: 'top top',
      end: '25% top',
      scrub: 1,
      onEnter: () => {
        gsap.to(problemSection, {
          width: '100%',
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
      start: '25% top',
      end: '50% top',
      scrub: 1,
      onEnter: () => {
        gsap.to(solutionSection, {
          width: '100%',
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

  // Team section scroll trigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: '50% top',
      end: '75% top',
      scrub: 1,
      onEnter: () => {
        gsap.to(teamSection, {
          width: '100%',
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
        gsap.to(teamSection, {
          width: '32px',
          height: '32px',
          left: 0,
          top: '50%',
          x: '-50%',
          y: 88,
          filter: 'grayscale(1) contrast(0)',
          clipPath: 'circle(32px)',
          duration: 1.2,
          ease: 'power2.inOut',
          borderRadius: '50%',
        })
      },
    },
  })

  // Roadmap section scroll trigger
  gsap.timeline({
    scrollTrigger: {
      trigger: '.scroll',
      start: '75% top',
      end: '100% top',
      scrub: 1,
      onEnter: () => {
        gsap.to(roadmapSection, {
          width: '100%',
          maxHeight: '500vh',
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
        gsap.to(roadmapSection, {
          width: '32px',
          maxHeight: '32px',
          left: 0,
          top: '50%',
          x: '-50%',
          y: 132,
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
  <Loading v-if="showLoading" :is-loading="isLoading" @complete="handleLoadingComplete" />
  <div class="scroll"></div>
  <div class="app">
    <img :src="logo" alt="logo" class="logo" />
    <Hero />
    <div class="dots">
      <Problem />
      <Solution />
      <Team />
    </div>
  </div>
  <Roadmap />
</template>

<style scoped>
.scroll {
  height: 500vh;
}

.app {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;

  .logo {
    position: fixed;
    top: 1vh;
    left: 3vw;
    z-index: 100;
  }

}
</style>
