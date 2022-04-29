<script>
	import Button from '$lib/components/button.svelte';

	let hovering = null;
	let status = null;

	async function handleStatus(hover = null, currentStatus = null) {
		if (hover && currentStatus) {
			hovering = hover; // true when on:mouseenter on pro icon
			status = currentStatus;

			// console.log(hover, currentStatus);
		} else if (!hover && currentStatus === null) {
			hovering = hover;
			status = currentStatus;
			// console.log(hovering, hover);
		} else if (hover === null && currentStatus) {
			hovering = hover;
			status = currentStatus;
			console.log(hovering, hover);
		} else if (hover === null && !currentStatus) {
			setTimeout(() => {
				hovering = hover;
				status = currentStatus;
			}, 3000);
		}
	}
</script>

<section
	on:mouseenter={() => handleStatus(true, true)}
	on:mouseleave={() => handleStatus(false, ...[,])}
	id="profileIcon"
	class="md:grid self-start absolute right-2 hidden"
>
	<Button>
		<svelte:fragment slot="profile" let:proSvg>{@html proSvg}</svelte:fragment>
	</Button>
</section>
{#if hovering || status}
	<section
		on:mouseenter={() => handleStatus(...[,], true)}
		on:mouseleave={() => handleStatus(...[,], false)}
		id="submenu"
		class="bg-neutral-900 absolute right-20 top-8 rounded-lg grid"
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
</style>
