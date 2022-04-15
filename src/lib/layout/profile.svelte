<script>
	import Button from '$lib/components/button.svelte';

	let hovering;

	function enter() {
		hovering = true;
	}
	function leave() {
		hovering = false;
	}

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section on:mouseenter={enter} on:mouseleave={leave} id="profile" class="grid self-start">
	<Button>
		<p class="inline" slot="profile" let:proSvg>{@html proSvg}</p>
	</Button>

	{#if hovering}
		<section id="submenu" class="absolute right right-0 mt-20 mr-4 rounded-lg grid">
			<Button on:click={handleMessage} let:proName>
				<p slot="profileLinks" class="inline">{proName}</p>
			</Button>
		</section>
	{/if}
</section>

<style>
	#profile {
		grid-area: profile;
	}
	#submenu {
		background-image: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.25));
	}
</style>
