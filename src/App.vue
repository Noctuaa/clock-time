<template>
	<div id="app">
		<div class="container clock-time">
			<div class="row">
				<div class="clock-container col-12">
					<Clock v-show="!toggleClock" :hours="this.hours" :minutes="this.minutes" :seconds="this.seconds">
					</Clock>
					<ClockDigital v-show="toggleClock" :hours="this.hours" :minutes="this.minutes"
						:seconds="this.seconds"></ClockDigital>
				</div>
			</div>
			<div class="row">
				<div class="clock_options col-12">
					<input type="checkbox" id="toggle" class="switch" v-model="toggleClock">
					<label for="toggle" class="toggle">
						<span class="toggle_handler"></span>
					</label>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import Clock from './components/Clock';
	import ClockDigital from './components/ClockDigital';

	export default {
		name: 'App',
		components: {
			Clock,
			ClockDigital
		},
		data() {
			return {
				day: Date,
				hours: '',
				minutes: '',
				seconds: '',
				toggleClock: false,
			}
		},

		methods: {
			/**
			 * Récupère le temps avec un interval.
			 */
			getTimes() {
				setInterval(() => {
					this.day = new Date();
					this.hours = this.day.getHours();
					this.minutes = this.day.getMinutes();
					this.seconds = this.day.getSeconds();
				});
			}
		},

		created() {
			this.getTimes();
		}
	}
</script>

<style>
	@import './assets/css/styles.css';
</style>