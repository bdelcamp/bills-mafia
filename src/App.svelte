<script>
	import SoundByte from './SoundByte.svelte'
	import AudioPlayer, { stopAll } from './AudioPlayer.svelte'
	
	let audioTracks = [
		{
			name: "Bills Mafia",
			src: "https://bldsh-public.s3.amazonaws.com/bills_mafia.webm"
		},
		{
			name: "Shout",
			src: "https://bldsh-public.s3.amazonaws.com/bills_shout.webm"
		}
	]
</script>

<main>
	<script>

	</script>
	
	<button on:click={stopAll}>
		Stop all!
	</button>
	
	{#each audioTracks as {name, src}}
	<div>
		<span>{name}</span>
		<AudioPlayer {src} />
	</div>
	{/each}

</main>



<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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