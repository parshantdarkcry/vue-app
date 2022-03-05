<template>
    <div class="hello">
        <h3>{{ msg }}</h3>
        <div class="frame">
            <div class="human">
                <div class="face"></div>
                <div class="hands">
                    <div class="hand hand-left"><div class="hand"></div></div>
                    <div class="hand hand-right"><div class="hand"></div></div>
                </div>
                <div class="body"></div>
                <div class="bottom">
                    <div class="leg left-left"></div>
                    <div class="leg left-right"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
    @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
    padding: 20px;
}
// delete the following line if no text is used
// edit the line if you wanna use other fonts
@import url(https://fonts.googleapis.com/css?family=Open+Sans:700,300);

// use only the available space inside the 400x400 frame
.frame {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 200px;
    height: 300px;
    margin-top: -100px;
    margin-left: -100px;
    margin-bottom: -100px;
    margin-right: -100px;
    border-radius: 2px;
    box-shadow: 4px 8px 16px 0 rgba(0, 0, 0, 0.1);
    overflow: hidden;
    color: #333;
    font-family: 'Open Sans', Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: #8e44ad;
    display: grid;
    place-items: center;

    .human {
        position: relative;

        .face {
            width: 40px;
            height: 40px;
            background: white;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -250%);
            border-radius: 50%;
        }
        .hand {
            height: 60px;
            width: 15px;
            background: white;
            border-radius: 10px;
        }
        .hand-left {
            position: absolute;
            top: 50%;
            left: 50%;
            transform-origin: 0 0;
            transform: translate(-200%, -85%) rotate(14deg);

            div {
                height: 50px;
                position: absolute;
                top: 50%;
                left: 50%;
                transform-origin: 0 0;
                transform: translate(-58%, 30%) rotate(-7deg);
            }
        }
        .hand-right {
            position: absolute;
            top: 50%;
            left: 50%;
            transform-origin: 0 0;
            transform: translate(110%, -62%) rotate(-70deg);
            animation-name: hand-right-up;
            animation-duration: 2s;
            animation-timing-function: linear;
            animation-iteration-count: infinite;
            animation-fill-mode: alternate-reverse;

            div {
                height: 50px;
                position: absolute;
                top: 50%;
                left: 50%;
                transform-origin: 0 0;
                transform: translate(-25%, 60%) rotate(-90deg);
                animation-name: handUp;
                animation-duration: 2s;
                animation-timing-function: linear;
                animation-iteration-count: infinite;
            }
        }
        .body {
            width: 57.5px;
            height: 100px;
            background: white;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 5px 5px 0px 0px;
        }
        .bottom {
            width: 56px;
            height: 100px;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, 30%);

            .leg {
                position: absolute;
                top: 0%;
                left: 50%;
                transform: translate(-50%, 0%);
                width: 48.5%;
                height: 100%;
                background: white;
                border-radius: 0px 0px 20px 20px;
            }
            .left-left {
                transform: translate(-106%, 0%);
            }
            .left-right {
                transform: translate(8%, 0%);
            }
        }
    }
}
@keyframes hand-right-up {
    0%,
    100% {
        transform: translate(110%, -62%) rotate(-70deg);
    }
    50% {
        transform: translate(90%, -60%) rotate(-90deg);
    }
}
@keyframes handUp {
    0%,
    100% {
        transform: translate(-25%, 60%) rotate(-90deg);
    }
    50% {
        transform: translate(-30%, 65%) rotate(-120deg);
    }
}
</style>
