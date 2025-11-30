<script setup lang="ts">
import { ref, onMounted } from 'vue'

const props = defineProps<{
  isLoading: boolean
}>()

const progress = ref(0)
const showContent = ref(true)

onMounted(() => {
  // Simulate loading progress
  const interval = setInterval(() => {
    if (progress.value < 100) {
      progress.value += Math.random() * 15
      if (progress.value > 100) progress.value = 100
    } else {
      clearInterval(interval)
    }
  }, 100)
})

// Watch for loading completion to trigger fade out
const emit = defineEmits<{
  complete: []
}>()

const handleComplete = () => {
  showContent.value = false
  setTimeout(() => {
    emit('complete')
  }, 800)
}

// Auto complete when progress reaches 100
const checkProgress = () => {
  if (progress.value >= 100 && props.isLoading === false) {
    handleComplete()
  }
}

// Watch both progress and isLoading
onMounted(() => {
  const checker = setInterval(() => {
    checkProgress()
  }, 100)

  return () => clearInterval(checker)
})
</script>

<template>
  <Transition name="fade">
    <div v-if="showContent" class="loading-screen">
      <div class="loading-content">
        <!-- Logo/Icon -->
        <div class="logo-container">
          <div class="logo-circle">
            <span class="logo-text">AI</span>
          </div>
          <div class="orbit-ring"></div>
        </div>

        <!-- Project Title -->
        <h1 class="loading-title">AI500 Project</h1>
        <p class="loading-subtitle">Умный полив и планирование посевов</p>

        <!-- Progress Bar -->
        <div class="progress-container">
          <div class="progress-bar">
            <div class="progress-fill" :style="{ width: `${progress}%` }"></div>
          </div>
          <span class="progress-text">{{ Math.round(progress) }}%</span>
        </div>
      </div>

      <!-- Background Elements -->
      <div class="bg-circle circle-1"></div>
      <div class="bg-circle circle-2"></div>
      <div class="bg-circle circle-3"></div>
    </div>
  </Transition>
</template>

<style scoped>
.loading-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(170.24deg, #2a2a2a 43.28%, #000000 75.36%);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  overflow: hidden;
}

.loading-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
  z-index: 2;
}

/* Logo Animation */
.logo-container {
  position: relative;
  width: 160px;
  height: 160px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-circle {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: #e0f540;
  border: 3px solid #898989;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 2;
  animation: pulse 2s ease-in-out infinite;
}

.logo-text {
  font-family: 'Kalnia', sans-serif;
  font-size: 48px;
  font-weight: 400;
  color: #000000;
  text-transform: uppercase;
}

.orbit-ring {
  position: absolute;
  width: 160px;
  height: 160px;
  border-radius: 50%;
  border: 2px solid #898989;
  animation: rotate 3s linear infinite;
}

.orbit-ring::after {
  content: '';
  position: absolute;
  top: 50%;
  right: 0;
  transform: translate(50%, -50%);
  width: 20px;
  height: 20px;
  background: #e0f540;
  border: 2px solid #898989;
  border-radius: 50%;
}

/* Text */
.loading-title {
  font-family: 'Kalnia', sans-serif;
  font-size: 64px;
  font-weight: 400;
  color: #e0f540;
  text-transform: uppercase;
  margin: 0;
  animation: fadeInUp 0.8s ease-out;
}

.loading-subtitle {
  font-family: 'Livvic', sans-serif;
  font-size: 24px;
  font-weight: 300;
  color: #ffffff;
  margin: 0;
  animation: fadeInUp 0.8s ease-out 0.2s backwards;
}

/* Progress Bar */
.progress-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  width: 400px;
  animation: fadeInUp 0.8s ease-out 0.4s backwards;
}

.progress-bar {
  width: 100%;
  height: 4px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 2px;
  overflow: hidden;
  position: relative;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #e0f540 0%, #c5d936 100%);
  border-radius: 2px;
  transition: width 0.3s ease;
  box-shadow: 0 0 10px rgba(224, 245, 64, 0.5);
}

.progress-text {
  font-family: 'Livvic', sans-serif;
  font-size: 18px;
  font-weight: 300;
  color: #e0f540;
}

/* Background Circles */
.bg-circle {
  position: absolute;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.05);
  pointer-events: none;
}

.circle-1 {
  width: 600px;
  height: 600px;
  top: -200px;
  left: -200px;
  animation: float 8s ease-in-out infinite;
}

.circle-2 {
  width: 400px;
  height: 400px;
  bottom: -100px;
  right: -100px;
  animation: float 6s ease-in-out infinite reverse;
}

.circle-3 {
  width: 800px;
  height: 800px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: float 10s ease-in-out infinite;
}

/* Animations */
@keyframes pulse {
  0%, 100% {
    transform: scale(1);
    box-shadow: 0 0 0 rgba(224, 245, 64, 0.4);
  }
  50% {
    transform: scale(1.05);
    box-shadow: 0 0 30px rgba(224, 245, 64, 0.6);
  }
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes float {
  0%, 100% {
    transform: translate(0, 0);
  }
  25% {
    transform: translate(20px, -20px);
  }
  50% {
    transform: translate(-10px, 10px);
  }
  75% {
    transform: translate(-20px, -10px);
  }
}

/* Fade Transition */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
