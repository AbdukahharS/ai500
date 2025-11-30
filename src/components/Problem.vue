<script setup lang="ts">
import Problem1 from '../assets/problem1.mp4'
import Problem2 from '../assets/problem2.mp4'
import Problem3 from '../assets/problem3.mp4'
import { onMounted } from 'vue'

onMounted(() => {
  const problemItems = document.querySelectorAll('.problem-item')

  if (problemItems) {
    problemItems.forEach((item) => {
      item.addEventListener('mouseenter', () => {
        const video = item.querySelector('video') as HTMLVideoElement
        if (video) {
          setTimeout(() => {
            video.play()
          }, 400)
        }
      })

      item.addEventListener('mouseleave', () => {
        const video = item.querySelector('video') as HTMLVideoElement
        if (video) {
          video.pause()
          video.currentTime = 0
        }
      })
    })
  }
})
</script>

<template>
  <section id="problem">
    <div class="circle"></div>
    <h2>ПРОБЛЕМА</h2>
    <div class="problem-item left">
      <p>Перерасход воды</p>
      <video :src="Problem1" muted loop></video>
    </div>
    <div class="problem-item top">
      <p>Сложность планирования в жарком климате</p>
      <video :src="Problem2" muted loop></video>
    </div>
    <div class="problem-item bottom">
      <video :src="Problem3" muted loop></video>
      <p>Низкая эффективность полива</p>
    </div>
    <div class="line"></div>
  </section>
</template>

<style scoped>
#problem {
  position: absolute;
  overflow: hidden;
  clip-path: circle(100%);
  width: 100vw;
  height: 100vh;
  left: 0;
  top: 0;
  z-index: 10;
  will-change: transform, filter, width, height;

  .line {
    height: 1px;
    width: 100vw;
    position: absolute;
    left: 0;
    bottom: 100px;
    z-index: 2;
    background: #fff;
  }

  .problem-item {
    position: absolute;
    z-index: 2;

    p {
      font-family: 'Livvic', sans-serif;
      color: #fff;
      font-weight: 300;
      font-size: 40px;
      transition: all 0.4s ease-in-out;
      z-index: 2;
      position: relative;
    }

    video {
      width: 146px;
      height: 146px;
      border-radius: 50%;
      object-fit: cover;
      transition: all 0.4s ease-in-out;
      filter: brightness(0.5);
      z-index: 1;
      display: block;
    }

    &.left {
      top: 50%;
      left: 10%;

      video {
        transform: translateX(40px);
        margin-top: -60px;
        margin-left: auto;
      }

      &:hover {
        video {
          width: 260px;
          height: 260px;
          filter: brightness(1);
          transform: translateX(100%);
        }

        p {
          font-size: 48px;
        }
      }
    }
    &.top {
      top: 30%;
      left: 50%;

      video {
        transform: translateX(40px);
        margin-top: -40px;
        margin-left: 100px;
      }

      &:hover {
        video {
          width: 260px;
          height: 260px;
          filter: brightness(1);
          transform: translateX(50%);
        }

        p {
          font-size: 48px;
        }
      }
    }
    &.bottom {
      bottom: 150px;
      left: 50%;
      transform: translateX(-50%);

      video {
        transform: translateX(40px);
        /* margin-top: -150px; */
        margin-left: auto;
      }

      p {
        margin-top: -44px;
      }

      &:hover {
        video {
          /* margin-top: -270px; */
          width: 260px;
          height: 260px;
          filter: brightness(1);
          transform: translateX(70%);
        }

        p {
          font-size: 48px;
        }
      }
    }
  }

  h2 {
    font-family: 'Livvic', sans-serif;
    color: #e0f540;
    font-weight: 300;
    font-size: 100px;
    z-index: 2;
    position: relative;
    top: 10%;
    left: 12%;
    width: fit-content;

    &::before {
      content: '';
      position: absolute;
      bottom: -10px;
      height: 2px;
      background: #d9d9d9;
      width: 50vw;
      right: -50px;
    }

    &::after {
      content: '';
      position: absolute;
      bottom: -10px;
      height: 35px;
      right: -50px;
      transform: translateX(50%) translateY(50%);
      border-radius: 50%;
      width: 35px;
      background: #d9d9d9;
    }
  }

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('../assets/problem-bg.png');
    background-size: cover;
    filter: brightness(0.3);
    z-index: 1;
  }

  .circle {
    position: absolute;
    height: 81vw;
    width: 81vw;
    border-radius: 50%;
    left: 0;
    border: 2px solid #898989;
    z-index: 2;
    top: 50%;
    transform: translateY(-50%) translateX(-25%);
  }
}
</style>
