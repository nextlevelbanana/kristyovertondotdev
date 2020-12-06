<script>
	export let name;
	let show;

	//shamely copied directly from the Svelte REPL
 	function clickOutside(node) {
 
		const handleClick = event => {
			if (node && !node.contains(event.target) && !event.defaultPrevented) {
			node.dispatchEvent(
				new CustomEvent('click_outside', node)
			)
			}
		}

		document.addEventListener('click', handleClick, true);
	
		return {
			destroy() {
				document.removeEventListener('click', handleClick, true);
			}
		}
	}
</script>

<style>
	.container {
		display: inline-block;
	}
	.trigger {
		color: #00843D;
		cursor: pointer;
	}
</style>

<div class="container">
	<div class="trigger" use:clickOutside on:click_outside={() => show = false} on:click={() => show = !show}>
		{name}
	</div>
	{#if show}
		<div class="slot">
			<slot></slot>
		</div>
	{/if}
</div>