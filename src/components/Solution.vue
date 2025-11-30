<script setup lang="ts">
import bgLogo from '../assets/bg-logo.svg'
import Solution1 from '../assets/solution1.mp4'
import Solution2 from '../assets/solution2.mp4'
import Solution3 from '../assets/solution3.mp4'
import Solution4 from '../assets/solution4.mp4'
import GlassSurface from './GlassSurface.vue'

const solutions = [
  {
    video: Solution1,
    title: 'Анализ погоды',
    desciption:
      'Интеграция с метеослужбами для прогнозирования осадков и температуры',
    list: ['Прогноз на 14 дней', 'Анализ микроклимата', 'Оповещения о погоде'],
  },
  {
    video: Solution2,
    title: 'Расчёт потребности в воде',
    desciption:
      'AI рассчитывает точный объем воды для каждого участка',
    list: [
      'Учет типа почвы',
      'Фазы роста растений',
      'Оптимизация расхода',
    ],
  },
  {
    video: Solution3,
    title: 'Рекомендации по срокам посев',
    desciption:
      'Умные рекомендации на основе климата и исторических данных',
    list: [
      'Оптимальные даты',
      'Севооборот',
      'Прогноз урожая',
    ],
  },
  {
    video: Solution4,
    title: 'Экономия ресурсов',
    desciption:
      'Снижение расходов на воду и электроэнергию до 40%',
    list: [
      'Мониторинг затрат',
      'Отчёты экономии',
      'ROI калькулятор',
    ],
  },
]
</script>

<template>
  <section id="solution">
    <img :src="bgLogo" alt="Logo" class="bg-log" />
    <div class="circle"></div>
    <h2>НАШЕ РЕШЕНИЕ</h2>
    <div class="line"></div>
    <div class="cards">
      <div v-for="(solution, index) in solutions" :key="index" class="card">
        <video :src="solution.video" muted loop></video>
        <div class="curtain"></div>

        <div class="content">
          <div>
            <h3>{{ solution.title }}</h3>
            <p>{{ solution.desciption }}</p>
          </div>
          <div class="list-container">
            <GlassSurface :width="300" :height="124" :displace="5" :border-radius="18" />
            <ul>
              <li v-for="(item, idx) in solution.list" :key="idx">
                {{ item }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
#solution {
  position: absolute;
  overflow: hidden;
  z-index: 20;
  will-change: transform, filter, width, height, clip-path, border-radius;
  background: linear-gradient(170.24deg, #2a2a2a 43.28%, #000000 75.36%);

  .cards {
    position: absolute;
    height: 47vh;
    width: fit-content;
    display: flex;
    flex-direction: row;
    gap: 0;
    bottom: 40%;
    left: 15%;

    .card {
      width: 270px;
      position: relative;
      overflow: hidden;
      border-radius: 20px;
      transition: width 0.3s ease;

      &:not(:first-child) {
        margin-left: -10px;
      }

      .curtain {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.7);
        pointer-events: none;
        transition: background 0.3s ease;
      }

      &:hover {
        width: 332px;

        .curtain {
          background: rgba(0, 0, 0, 0.3);
        }

        .content p {
          opacity: 1;
        }

        .content .list-container {
          opacity: 1;
        }
      }

      .content {
        position: relative;
        z-index: 1;
        padding: 18px 16px;
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        justify-content: space-between;
        box-sizing: border-box;

        h3 {
          color: #fff;
          font-family: 'Livvic', sans-serif;
          font-weight: 300;
          font-size: 32px;
        }

        p {
          transition: opacity 0.5s ease 0.3s;
          margin-top: 20px;
          color: #fff;
          font-family: 'Arial', sans-serif;
          font-weight: 400;
          font-size: 18px;
          line-height: 20px;
          opacity: 0;
        }

        .list-container {
          position: relative;
          width: 300px;
          height: 124px;
          min-height: 124px;
          border-radius: 18px;
          background: #FFFFFF1A;
          opacity: 0;
          transition: opacity 0.5s ease 0.3s;

          ul {
            position: absolute;
            top: 8px;
            left: 28px;
            display: flex;
            flex-direction: column;
            width: calc(100% - 56px);
            height: calc(100% - 16px);
            justify-content: space-around;
            color: #fff;
            font-family: 'Arial', sans-serif;
            font-weight: 400;
            font-size: 20px;
          }
        }
      }

      video {
        width: 100%;
        height: 100%;
        object-fit: cover;
        position: absolute;
      }
    }
  }

  .bg-log {
    position: absolute;
    bottom: 2%;
    left: 75%;
    transform: translate(-50%, 0);
    height: 85%;
  }

  .circle {
    position: absolute;
    width: 32vw;
    height: 32vw;
    border-radius: 50%;
    border: 2px solid #e0f540;
    top: 0;
    right: 0;
    transform: translate(45%, -65%);
  }

  h2 {
    font-family: 'Livvic', sans-serif;
    font-weight: 300;
    font-size: 100px;
    line-height: 70px;
    letter-spacing: 0%;
    color: #e0f540;
    position: absolute;
    left: 10vw;
    bottom: 15%;

    &::before {
      content: '';
      position: absolute;
      width: 50vw;
      height: 2px;
      background: #fff;
      bottom: 50%;
      left: 0;
      transform: translate(-100%, 50%);
    }
    &::after {
      content: '';
      position: absolute;
      width: 26px;
      height: 26px;
      border-radius: 50%;
      background: #fff;
      bottom: 50%;
      left: 0;
      transform: translate(-100%, 50%);
    }
  }

  .line {
    position: absolute;
    width: 100vw;
    height: 1px;
    background: #e0f54066;
    bottom: 10%;
  }
}
</style>
