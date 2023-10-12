<script>
	import SoundByte from './SoundByte.svelte'
	import AudioPlayer, { stopAll } from './AudioPlayer.svelte'
	
	let audioTracks = [
		{
			name: "Bills Mafia",
			src: "https://bldsh-public.s3.amazonaws.com/bills_mafia.mp3"
		},
		{
			name: "Shout",
			src: "https://bldsh-public.s3.amazonaws.com/bills_shout.mp3"
		}
	]
</script>

<main>
	<div class="logo"/>

	<button on:click={stopAll} style="margin-bottom: 20px;">
		Stop all!
	</button>
	
	{#each audioTracks as {name, src}}
	<div class="player">
		<span class="name">{name}</span>
		<AudioPlayer {src} />
	</div>
	{/each}

</main>



<style>
	button {
		border: 1px solid red;
		background-color: red;
		width: 300px;
		padding: 5px;
		margin: 5px;
		color: white;
		border-radius: 5px;
	}

	button:hover {
		background-color: white;
		color: red;
	}

	button:active {
		background-color: #00338D;
		color: white;
	}

	.logo {
		display: block;
		width: 300px;
		height: 200px;
		margin: 0 auto;
		background-image: url('https://bldsh-public.s3.amazonaws.com/Buffalo_Bills_logo.jpg');
		background-repeat: no-repeat;
		background-size: 300px 200px	;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.player {
		background-color: #00338D;
		border-radius: 10px;
		width: 300px;
		padding-top: 10px;
		padding-bottom: 10px;
		margin: 0 auto;
		margin-bottom: 10px;
	}

	.player .name {
		color: white;
		font-weight: bold;
		font-size: +2;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
