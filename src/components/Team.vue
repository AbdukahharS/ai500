<script setup lang="ts">
import Top from '../assets/looper-top.svg'
import Left from '../assets/looper-left.svg'
import Right from '../assets/looper-right.svg'
import Figma from '../assets/figma.png'
import Photoshop from '../assets/photoshop.png'
import Swift from '../assets/swift.png'
import Kotlin from '../assets/kotlin.png'
import React from '../assets/react.png'
import Vue from '../assets/vue.png'
import Node from '../assets/nodejs.png'
</script>

<template>
  <section id="team">
    <img :src="Top" alt="Top Looper" class="looper top-looper" />
    <img :src="Left" alt="Left Looper" class="looper left-looper" />
    <img :src="Right" alt="Right Looper" class="looper right-looper" />
    <div class="circle top"></div>
    <div class="circle right"></div>
    <h2>КОМАНДА</h2>
    <div class="member designer">
      <h3>UI/UX Designer</h3>
      <div class="hr"></div>
      <div class="bot">
        <h4>Журабаев Асадбек</h4>
        <div>
          <img :src="Figma" alt="Figma" />
          <img :src="Photoshop" alt="Photoshop" />
        </div>
      </div>
    </div>
    <div class="member mobile">
      <h3>Mobile Developer</h3>
      <div class="hr"></div>
      <div class="bot">
        <h4>Инагамжанов Умар</h4>
        <div>
          <img :src="Swift" alt="Swift" />
          <img :src="Kotlin" alt="Kotlin" />
        </div>
      </div>
      <a href="http://inagamjanov.uz/" target="_blank" rel="noopener noreferrer"
        >https://inagamjanov.uz</a
      >
    </div>
    <div class="member web">
      <h3>Web Developer</h3>
      <div class="hr"></div>
      <div class="bot">
        <h4>Каххаров Шахзод</h4>
        <div>
          <img :src="React" alt="React" />
          <img :src="Vue" alt="Vue" />
          <img :src="Node" alt="Node.js" />
        </div>
      </div>
      <a href="https://abdukahhar.uz/" target="_blank" rel="noopener noreferrer"
        >https://abdukahhar.uz</a
      >
    </div>
  </section>
</template>

<style scoped>
#team {
  position: absolute;
  overflow: hidden;
  z-index: 30;
  will-change: transform, filter, width, height, clip-path, border-radius;
  background: #272727;

  .member {
    position: absolute;

    h3 {
      font-family: 'Livvic', sans-serif;
      font-weight: 300;
      font-size: 70px;
      line-height: 70px;
      letter-spacing: 0%;
      color: #e0f540;
    }

    .hr {
      width: 100%;
      height: 1px;
      background: #fff;
      margin: 20px 0;
    }

    .bot {
      display: flex;
      align-items: center;
      gap: 33px;

      h4 {
        font-family: 'Livvic', sans-serif;
        font-weight: 300;
        font-size: 32px;
        color: #ffffff;
      }

      div {
        display: flex;
        gap: 20px;

        img {
          width: 60px;
          height: 60px;
          object-fit: contain;
        }
      }
    }

    a {
        display: block;
        margin-top: 20px;
        font-family: 'Livvic', sans-serif;
        font-weight: 300;
        font-size: 24px;
        color: #ffffff;
        text-decoration: none;

        &:hover {
          text-decoration: underline;
        }
    }

    &.designer {
      top: 16vh;
      left: 8vw;
    }

    &.mobile {
      bottom: 27vh;
      left: 16vw;
    }

    &.web {
      bottom: 38vh;
      right: 10vw;
    }
  }

  h2 {
    font-family: 'Livvic', sans-serif;
    font-weight: 300;
    font-size: 100px;
    line-height: 70px;
    letter-spacing: 0%;
    color: #e0f540;
    position: absolute;
    top: 80px;
    right: 130px;

    &::before {
      content: '';
      position: absolute;
      width: 50vw;
      height: 2px;
      background: #fff;
      bottom: -40px;
      left: -50px;
    }

    &::after {
      content: '';
      position: absolute;
      width: 26px;
      height: 26px;
      border-radius: 50%;
      background: #fff;
      bottom: -40px;
      left: -50px;
      transform: translate(-100%, 50%);
    }
  }

  .looper {
    position: absolute;

    &.top-looper {
      top: 0;
      left: 0;
    }

    &.left-looper {
      bottom: 0;
      left: 0;
    }

    &.right-looper {
      bottom: 0;
      right: 0;
    }
  }

  .circle {
    position: absolute;
    width: 56vw;
    height: 56vw;
    border-radius: 50%;
    border: 2px solid #ffffff80;

    &.top {
      top: -34vw;
      left: -11vw;
      transform: rotate(-116deg);
    }

    &.right {
      bottom: -17vw;
      right: -10vw;
      transform: rotate(-116deg);
    }
  }
}
</style>
