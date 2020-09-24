<template>
    <div class="clock">
        <div class="hours" :style="{transform: 'rotateZ(' + degHours + 'deg)'}"></div>
        <div class="minutes" :style="{transform: 'rotateZ(' + degMinutes + 'deg)'}"></div>
        <div class="seconds" :style="{transform: 'rotateZ(' + degSeconds + 'deg)'}">
        </div>
        <div class="number" v-for="index in 12" :key="index" :class="'number' + index"></div>
    </div>
</template>

<script>
    export default {
        props: {
            hours: "",
            minutes: "",
            seconds: ""
        },

        computed: {
            /**
             * Calcul le degré de rotation de l'aiguille heure.
             * @returns {number} Degré 
             */
            degHours() {
                return (this.hours * 30) + (this.minutes / 12)
            },

            /**
             * Calcul le degré de rotation de l'aiguille minute.
             * @returns {number} Degré 
             */
            degMinutes() {
                return this.minutes * 6;
            },

            /**
             * Calcul le degré de rotation de l'aiguille seconde.
             * @returns {number} Degré 
             */
            degSeconds() {
                return this.seconds * 6;
            }
        }
    }
</script>

<style>
    .clock {
        height: 300px;
        width: 300px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        border: 4px solid rgba(5, 84, 150,1);
        box-shadow: 5px 5px 5px 0px rgba(0, 0, 0, 0.411),
            inset 5px 5px 5px 0px rgba(0, 0, 0, 0.411),
            5px -5px 5px 0px rgba(0, 0, 0, 0.411),
            inset 5px -5px 5px 0px rgba(0, 0, 0, 0.411);
        color: #fff;
        position: relative;
        font-size: 30px;
        margin-bottom: 40px;
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
        height: 100%;
        text-align: center;
        transform: rotate(var(--rotation));
        padding: 10px;
    }

    .clock .number::before {
        display: inline-flex;
        transform: rotate(var(--rotation));
        content: '12';
    }

    .clock .number1::before {
        content: '1';
        --rotation: -30deg;
    }

    .clock .number2::before {
        content: '2';
        --rotation: -60deg;
    }

    .clock .number3::before {
        content: '3';
        --rotation: -90deg;
    }

    .clock .number4::before {
        content: '4';
        --rotation: -120deg;
    }

    .clock .number5::before {
        content: '5';
        --rotation: -150deg;
    }

    .clock .number6::before {
        content: '6';
        --rotation: -180deg;
    }

    .clock .number7::before {
        content: '7';
        --rotation: -210deg;
    }

    .clock .number8::before {
        content: '8';
        --rotation: -240deg;
    }

    .clock .number9::before {
        content: '9';
        --rotation: -270deg;
    }

    .clock .number10::before {
        content: '10';
        --rotation: -300deg;
    }

    .clock .number11::before {
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
        width: 130px;
        height: 130px;
    }

    .clock .minutes {
        width: 160px;
        height: 160px;
    }

    .clock .seconds {
        width: 190px;
        height: 190px;
    }

    .clock .hours,
    .clock .minutes,
    .clock .seconds {
        display: flex;
        justify-content: center;
        position: absolute;
        border-radius: 50%;
    }

    .clock .hours:before {
        content: '';
        position: absolute;
        width: 8px;
        height: 70px;
        background-color: #ff105e;
        z-index: 10;
        border-radius: 6px 6px 0 0;
    }

    .clock .minutes:before {
        content: '';
        position: absolute;
        width: 4px;
        height: 80px;
        background-color: #fff;
        z-index: 11;
        border-radius: 6px 6px 0 0;
    }

    .clock .seconds:before {
        content: '';
        position: absolute;
        width: 2px;
        height: 130px;
        background-color: #fff;
        z-index: 12;
        border-radius: 6px 6px 0 0;
    }

</style>