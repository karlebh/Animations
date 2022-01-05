<template>
	<div>
		
		<!-- <div class="box green"></div>
		<div class="box orange"></div>
		<div class="box grey"></div>
		<button id="back">back</button> -->

	<div class="overlay">
		<div class="overlay-1"></div>
		<div class="overlay-2"></div>
		<div class="overlay-3"></div>
	</div>
	</div>
</template>

<style>
	.overlay {
		display: flex;
		position: fixed;
		left: 0;
		right: 0;
		bottom: 0;
		top: 0;
		background: rgba(0, 0, 0, 0);
		height: 100%;
	}

	.overlay-1 {
		flex: 1;
		background: #008080;
	}

	.overlay-2 {
		flex: 1;
		background: #009090;
	}

	.overlay-3 {
		flex: 1;
		background: #009595;
	}
	.box {
		width: 200px;
		height: 200px;
		background: linear-gradient(45deg, purple, teal);
		position: relative;
	}
</style>

<script>
	import gsap from 'gsap'

	export default {
		mounted() {
			// let tween = gsap.to('.green', {delay: .6, duration: 1, x: '-30rem', ease: 'back.out(1.7)'});
			// gsap.to(".orange", {delay: .8, duration: 1, rotationY: 360});
			// gsap.to(".grey", {delay: .9, duration: 1, x: 100, y: 100, skewX: 45, rotation: 180});
			// document.getElementById('back').onclick = () => tween.reverse()

			gsap.to('.overlay-1', {y: '-100vh', delay: .9})
			gsap.to('.overlay-2', {y: '-100vh', delay: .7})
			gsap.to('.overlay-3', {y: '-100vh', delay: .5})
			gsap.to('.overlay', {y: '-100vh', delay: .9})

		}
	}

</script>