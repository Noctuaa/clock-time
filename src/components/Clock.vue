<template>
    <div class="clock">
        <div class="hours" :style="{transform: 'rotateZ(' + (this.hours + (this.minutes/12)) + 'deg)'}"></div>
        <div class="minutes" :style="{transform: 'rotateZ(' + this.minutes + 'deg)'}"></div>
        <div class="seconds" :style="{transform: 'rotateZ(' + this.seconds + 'deg)'}">
        </div>
        <div class="number" v-for="index in 12" :key="index" :class="'number' + index"></div>
    </div>
</template>

<script>
    export default {
        props: {
            day: "",
            hours: "",
            minutes: "",
            seconds: ""
        }
    }
</script>

<style>
    .clock {
        height: 350px;
        width: 350px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        border: 4px solid rgb(89, 89, 194);
        box-shadow: 5px 5px 5px 0px rgba(0, 0, 0, 0.411),
            inset 5px 5px 5px 0px rgba(0, 0, 0, 0.411),
            5px -5px 5px 0px rgba(0, 0, 0, 0.411),
            inset 5px -5px 5px 0px rgba(0, 0, 0, 0.411);
        color: #fff;
        position: relative;
        font-family: 'Rubik', sans-serif;
        font-size: 30px;
    }

    .clock:before {
        content: '';
        position: absolute;
        width: 15px;
        height: 15px;
        background-color: #fff;
        border-radius: 50%;
        z-index: 100;
    }

    .clock .number {
        --rotation: 0;
        position: absolute;
        width: 100%;
        height: 100%;
        text-align: center;
        transform: rotate(var(--rotation));
        padding: 10px;
    }

    .number::before{
        display: inline-flex;
        transform: rotate(var(--rotation));
        content: '12';
    }

    .number1::before {
        content: '1';
        --rotation: -30deg;
    }

    .number2::before {
        content: '2';
        --rotation: -60deg;
    }

    .number3::before {
        content: '3';
        --rotation: -90deg;
    }

    .number4::before {
        content: '4';
        --rotation: -120deg;
    }

    .number5::before {
        content: '5';
        --rotation: -150deg;
    }

    .number6::before {
        content: '6';
        --rotation: -180deg;
    }

    .number7::before {
        content: '7';
        --rotation: -210deg;
    }

    .number8::before {
        content: '8';
        --rotation: -240deg;
    }

    .number9::before {
        content: '9';
        --rotation: -270deg;
    }

    .number10::before {
        content: '10';
        --rotation: -300deg;
    }

    .number11::before {
        content: '11';
        --rotation: -330deg;
    }

    .clock .number1 {
        --rotation: 30deg
    }

    .clock .number2 {
        --rotation: 60deg
    }

    .clock .number3 {
        --rotation: 90deg
    }

    .clock .number4 {
        --rotation: 120deg
    }

    .clock .number5 {
        --rotation: 150deg
    }

    .clock .number6 {
        --rotation: 180deg
    }

    .clock .number7 {
        --rotation: 210deg
    }

    .clock .number8 {
        --rotation: 240deg
    }

    .clock .number9 {
        --rotation: 270deg
    }

    .clock .number10 {
        --rotation: 300deg
    }

    .clock .number11 {
        --rotation: 330deg
    }






    .clock .hours {
        width: 160px;
        height: 160px;
    }

    .clock .minutes {
        width: 190px;
        height: 190px;
    }

    .clock .seconds {
        width: 230px;
        height: 230px;
    }

    .hours,
    .minutes,
    .seconds {
        display: flex;
        justify-content: center;
        position: absolute;
        border-radius: 50%;
    }

    .hours:before {
        content: '';
        position: absolute;
        width: 8px;
        height: 80px;
        background-color: #ff105e;
        z-index: 10;
        border-radius: 6px 6px 0 0;
    }

    .minutes:before {
        content: '';
        position: absolute;
        width: 4px;
        height: 90px;
        background-color: #fff;
        z-index: 11;
        border-radius: 6px 6px 0 0;
    }

    .seconds:before {
        content: '';
        position: absolute;
        width: 2px;
        height: 150px;
        background-color: #fff;
        z-index: 12;
        border-radius: 6px 6px 0 0;
    }
</style>