<script setup lang="ts">
import { onMounted } from 'vue'
import logo from './assets/logo.svg'
import Hero from './components/Hero.vue'
import Problem from './components/Problem.vue'

onMounted(() => {
  const problemSection = document.getElementById('problem')

  window.addEventListener('scroll', () => {
    const scroll = window.scrollY
    const height = window.innerHeight
    const ratio = (height * 2) / 5
    if (problemSection) {
      if (scroll > ratio && scroll < 2 * ratio) {
        problemSection.classList.add('active')
      } else {
        problemSection.classList.remove('active')
      }
    }
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
