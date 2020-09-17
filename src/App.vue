<template>
	<div id="app">
		<div class="container">
			<div class="row clock-container">
				<Clock :day="this.day" :hours="this.hours" :minutes="this.minutes" :seconds="this.seconds"></Clock>
			</div>
		</div>
	</div>
</template>

<script>
import Clock from './components/Clock';

	export default {
		name: 'App',
		components: {
			Clock
		},
		data(){
			return{
				day : Date,
				hours: Number,
				minutes: Number,
				seconds: Number,
			}
		},
		created() {			
			setInterval(() => {
				this.day = new Date();
				this.hours = this.day.getHours() * 30;
				this.minutes = this.day.getMinutes() * 6;
				this.seconds = this.day.getSeconds() * 6;
			},1000);
		}
	}
</script>

<style>
	@import './assets/css/styles.css';
</style>