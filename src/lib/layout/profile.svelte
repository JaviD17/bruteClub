<script>
	import Button from '$lib/components/button.svelte';

	let clicked = null;
	let status = null;

	let leave = () => {
		clicked = !clicked;
	};

	function handleClick() {
		clicked = !clicked;
	}
</script>

<section on:click={handleClick} id="profileIcon" class="md:grid self-start absolute right-2 hidden">
	<Button>
		<svelte:fragment slot="profile" let:proSvg>{@html proSvg}</svelte:fragment>
	</Button>
</section>
{#if clicked}
	<section
		on:mouseleave={leave}
		id="submenu"
		class="bg-neutral-800/80 absolute top-8 rounded-lg grid py-4 px-1 shadow shadow-neutral-800"
	>
		<Button on:click let:proName>
			<p slot="profileLinks" class="inline">{proName}</p>
		</Button>
	</section>
{/if}

<style>
	#profileIcon {
		grid-area: profile;
	}
	#submenu {
		right: 1rem;
		top: 5.5rem;

	}
</style>
