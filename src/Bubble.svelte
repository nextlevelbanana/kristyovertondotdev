<script>
	import { fly, fade } from 'svelte/transition';
	import { backOut } from 'svelte/easing';
	export let bubbles;
</script>

<style>
	.bubble {
		border-radius: 1rem;
		background-color: #0066A4;
		padding: 1.5rem;
		color: white;
		margin: 1rem;
		display: flex;
		-webkit-box-shadow: -3px 3px 15px 3px rgba(0,0,0,0.45); 
		box-shadow: -3px 3px 15px 3px rgba(0,0,0,0.45);

	}
	.container {
		position: fixed;
	}
</style>

<div class="container">
	{#each bubbles as bubble, index}
	<div class="bubble" in:fly={{x: -500, duration: 900, delay: 1200*index, easing:backOut}} out:fade={{duration:200}}>
			{bubble}
	</div>
	{/each}
</div>