<script>
	import Button from '$lib/components/button.svelte';

	let hovering;

	// let delay = () => {
	// 	setTimeout()
	// }

	function enter() {
		hovering = true;
	}
	function leave() {
		// hovering = false;
		setTimeout(() => {
			hovering = false
		}, 2000);

	// 	setTimeout(() => {
    //   greet = true;
    // }, 2000)
	}

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section
	on:mouseenter={enter}
	on:mouseleave={leave}
	id="profileIcon"
	class="md:grid self-start absolute right-2 hidden"
>
	<Button>
		<svelte:fragment slot="profile" let:proSvg>{@html proSvg}</svelte:fragment>
	</Button>

	{#if hovering}
		<section id="submenu" class="bg-neutral-900 absolute right-20 top-4 rounded-lg grid">
			<Button on:click={handleMessage} let:proName>
				<p slot="profileLinks" class="inline">{proName}</p>
			</Button>
		</section>
	{/if}
</section>

<style>
	#profileIcon {
		grid-area: profile;
	}
</style>
