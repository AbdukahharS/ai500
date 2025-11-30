<script setup lang="ts">
import logo from '../assets/logo.svg'
import video from '../assets/hero-bg.mp4'
import GlassSurface from './GlassSurface.vue';
</script>

<template>
    <section id="hero">
        <video :src="video" autoplay loop muted>
        </video>
        <div class="curtain"></div>
        <div class="glasses">
            <div class="glass" v-for="value in 29" :key="value"></div>
        </div>
        <div class="circle">
            <div class="orbit-wrapper" :style="{ transform: `rotate(195deg)` }">
                <div class="orbit"></div>
            </div>
        </div>
        <img :src="logo" alt="logo" class="logo">
        <div class="content">
            <div class="top">
                <h1>AI</h1>
                <h2>СЕРВИС УМНОГО ПОЛИВА И ПЛАНИРОВАНИЯ ПОСЕВОВ</h2>
            </div>
            <div class="bottom">
                <div class="info">
                    <div class="dot"></div>
                    <h3>«Экономьте воду и повышайте урожайность <br>благодаря анализу погоды и рекомендациям ИИ</h3>
                </div>
                <div class="buttons">
                    <GlassSurface :height="48" :width="296" :border-radius="24" :distortion-scale="10"><button class="white">Попробовать демо</button></GlassSurface>
                    <GlassSurface :height="48" :width="296" :border-radius="24":distortion-scale="10"><button class="yellow">Узнать больше</button></GlassSurface>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
#hero {
    position: relative;
    overflow: hidden;

    .content {
        position: absolute;
        top: 50%;
        left: 53%;
        transform: translate(-50%, -50%);
        z-index: 4;

        .top {
            display: flex;
            flex-direction: row;

            h1 {
                font-family: 'Kalnia', sans-serif;
                font-size: 240px;
                font-weight: 400;
                text-transform: uppercase;
                color: #E0F540;
                line-height: 100%;
            }

            h2 {
                font-family: 'Livvic', sans-serif;
                font-size: 52px;
                font-weight: 300;
                line-height: 70px;
                text-transform: uppercase;
                color: #FFFFFF;
                margin-top: 214px;
                width: 40vw;
                margin-left: 2vw;
            }
        }

        .bottom {
            margin-top: 10vh;
            width: fit-content;
            margin-left: auto;

            .info {
                display: flex;
                flex-direction: row;
                align-items: center;
                gap: 20px;

                .dot {
                    width: 20px;
                    height: 20px;
                    background: #E0F540;
                    border-radius: 50%;
                }

                h3 {
                    font-family: 'Labrada', sans-serif;
                    font-size: 26px;
                    font-weight: 400;
                    line-height: 100%;
                    color: #FFFFFF;
                }
            }

            .buttons {
                margin-top: 24px;
                position: relative;
                display: flex;
                flex-direction: row;
                gap: 30px;
                
                button {
                    width: 296px;
                    padding: 12px 14px 14px 14px;
                    font-family: 'Labrada', sans-serif;
                    font-size: 22px;
                    font-weight: 400;
                    line-height: 100%;
                    border-radius: 24px;
                    color: #FFFFFF;
                    border: none;
                    cursor: pointer;
                    position: absolute;
                    top: 0;
                    
                    &.white {
                        background: #FFFFFF1A;
                    }

                    &.yellow {
                        background: #E4FF1633;
                    }
                }

            }
        }
    }

    video {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;

    }

    .curtain {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(0deg, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3));
        z-index: 1;
    }

    .glasses {
        position: absolute;
        top: 0;
        right: 0;
        height: 100%;
        display: flex;
        flex-direction: row;
        z-index: 3;

        .glass {
            height: 100%;
            width: 16px;
            background: #D9D9D926;
            backdrop-filter: blur(123.4000015258789px);
            box-shadow: 0px 4px 4px 0px #00000040;

        }
    }

    .circle {
        position: absolute;
        height: 81vw;
        width: 81vw;
        border-radius: 50%;
        right: 0;
        border: 2px solid #898989;
        z-index: 2;
        top: 50%;
        transform: translateY(-50%);

        .orbit-wrapper {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            /* Let clicks pass through if needed */
        }

        .orbit {
            position: absolute;
            top: 50%;
            right: 0;
            /* Position on the right edge */
            transform: translate(50%, -50%);
            /* Center it on the border */
            width: 42px;
            height: 42px;
            background: #060705;
            border: 2px solid #898989;
            border-radius: 50%;
        }
    }

    .logo {
        position: absolute;
        top: 1vh;
        left: 3vw;
    }
}
</style>