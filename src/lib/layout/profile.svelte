<script>
	import Button from '$lib/components/button.svelte';

	let hovering;
	let status;

	// function enter() {
	// 	hovering = true;
	// }
	// function leave() {
	// 	if (!status) {
	// 		setTimeout(() => {
	// 			hovering = false;
	// 		}, 3000);
	// 	}
	// }

	function handleStatus(proHover = null, subHover = null) {
		// for hovering profile and submenu
	}

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section
	on:mouseenter={() => handleStatus()}
	on:mouseleave={() => handleStatus()}
	id="profileIcon"
	class="md:grid self-start absolute right-2 hidden"
>
	<Button>
		<svelte:fragment slot="profile" let:proSvg>{@html proSvg}</svelte:fragment>
	</Button>
</section>

{#if hovering}
	<section
		on:mouseenter={() => handleStatus(true, true)}
		on:mouseleave={() => handleStatus(false, false)}
		id="submenu"
		class="bg-neutral-900 absolute right-20 top-4 rounded-lg grid"
	>
		<Button on:click={handleMessage} let:proName>
			<p slot="profileLinks" class="inline">{proName}</p>
		</Button>
	</section>
{/if}

<style>
	#profileIcon {
		grid-area: profile;
	}
</style>
