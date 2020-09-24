<template>
    <div class="clock_digital">
        <div class="clock-col">
            <p class="hour">{{leadingZero(this.hours)}}</p>
            <p class="label">Hours</p>
        </div>
        <div class="clock-col">
            <p class="minutes">{{leadingZero(this.minutes)}}</p>
            <p class="label">Minutes</p>
        </div>
        <div class="clock-col">
            <p class="seconds">{{leadingZero(this.seconds)}}</p>
            <p class="label">Seconds</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            hours: "",
            minutes: "",
            seconds: "",
        },
        methods: {
            /**
             * On ajoute en premier un zéro si les heures, minutes ou secondes sont inférieur à dix.
             * @param {number} - Numéro du temps
             */
            leadingZero(time) {
                return (time < 10 ? '0' : '') + time;
            }
        },
    }
</script>

<style>
    .clock_digital {
        margin-bottom: 40px;
        display: flex;
        align-items: center;
        
        box-shadow: 0 0 0 1px rgba(0, 0, 0, .2);
    }

    .clock-col {
        position: relative;
        text-align: center;
        min-width: 90px;
    }

    .clock-col p:first-child {
        color: #fff;
        font-size: 5rem;
        text-shadow: 0 0 20px rgb(10, 175, 230), 0 0 20px rgba(10, 175, 230, 0);
        font-family: 'monospace';
        margin: 0px 40px;
    }

    .clock-col .label {
        color: #fff;
        font-size: 1rem;
        text-transform: uppercase;
        margin-top: 10px;
        background-color: #055496;
        box-shadow: 0 0 0 1px rgba(0, 0, 0, .2);
        height: 35px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .clock-col:not(:last-child) p::before {
        content: ':';
        color: #fff;
        font-size: 3rem;
        position: absolute;
        right: -13px;
        top: 15%;
        z-index: 10;
    }

    @media screen and (max-width: 576px) {
        .clock-col p:first-child {
            font-size: 3rem;
            margin: 0px 20px;
        }

        .clock-col:not(:last-child) p::before {
            font-size: 1.5rem;
            right: -9px;
        }

        .clock-col .label {
            font-size: .8rem;
            height: 25px;
        }
    }
</style>