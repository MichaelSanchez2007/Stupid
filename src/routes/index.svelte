<script>
	import BeamA from '../beam/BeamA.svelte';
	import { fade } from 'svelte/transition';
	import { onMount } from 'svelte';
	function windowcloser() {
		window.close();
	}
	let showBeam = false;
	let showFred = true;

	function toggleBeam() {
		showBeam = true;
		new Audio('Zaza.mp3').play();
		setTimeout(function () {
			new Audio('Dead.mp3').play();
		}, 3000);
		setTimeout(function () {
			TheEnd();
		}, 7000);
		showFred = false;
	}
	function TheEnd() {
		document.body.remove();
		document.documentElement.style.backgroundColor = 'black';
		const h1 = document.createElement('h1');
		h1.innerText = 'THE END OF THE FNAF MULTIVERSE';
		document.documentElement.appendChild(h1);
		h1.style.color = 'blue';
		document.documentElement.style.textAlign = 'center';
		h1.style.marginTop = '25vh';
	}
</script>

<div class="home-page">
	<header>
		<h1>&nbsp;&nbsp;FREDDY KING &nbsp;-VS-&nbsp; AMONG US</h1>
	</header>

	<div class="container">
		<h2>SELECTOR</h2>
		<button on:click={toggleBeam}>BEAMER</button>
		<button on:click={windowcloser}>DONT DO IT</button>

		<div class="fighters">
			{#if showFred}
				<img transition:fade={{ delay: 4000 }} class="freddy" src="/Fred.png" alt="" />
			{/if}

			{#if showBeam}
				<div transition:fade={{ delay: 2000 }} id="beam-a"><BeamA /></div>
			{/if}

			<div class="among">
				<img src="/Among.png" alt="" />
			</div>
		</div>
	</div>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Butcherman&display=swap');

	:global(body) {
		background: linear-gradient(180deg, #000000 0%, rgba(0, 0, 0, 0) 100%);
		background-repeat: no-repeat;
	}
	header {
		display: grid;
		font-style: normal;
		background: rgb(0, 0, 0);
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		width: 1000000px;
	}
	h1 {
		color: rgb(255, 0, 0);
		width: 550px;
		font-family: 'Butcherman', cursive;
		font-weight: 300;
		word-spacing: 10px;
	}
	.fighters {
		height: 470px;
		display: flex;
		flex-direction: column;
		padding: 1rem;
	}
	img {
		width: 100px;
		animation: 0.000001s infinite alternate hover;
	}
	.among {
		transform: translateX(-15px);
		margin: auto auto 10px auto;
		height: max-content;
		width: max-content;
	}
	.freddy {
		z-index: 3;
		position: relative;
		margin: 30px auto auto auto;
	}
	h2 {
		font-family: 'Butcherman', cursive;
		font-weight: 300;
		word-spacing: 10px;
		text-align: center;
		color: red;
	}
	.container {
		flex-direction: column;
		background: grey;
		border-radius: 30%;
		width: 600px;
		margin: auto;
	}
	button {
		font-weight: 900;
		margin: auto;
		display: flex;
		padding: 5px;
		color: royalblue;
		background: black;
		cursor: pointer;
	}
	#beam-a {
		background: red;
		position: absolute;
		margin: auto;
		right: 0;
		left: 0;
		bottom: 300px;
		width: max-content;
		z-index: 2;
		border-radius: 100%;
	}
	@keyframes hover {
		0% {
			transform: translate(0.5%);
		}
		100% {
			transform: translate(0%);
		}
	}
</style>
