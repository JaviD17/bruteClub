<script>
	import Button from '$lib/components/button.svelte';

	export let active;
</script>

<nav class="hidden md:nav">
	<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
</nav>

{#if active}
	<nav class="nav-mobile md:hidden bg-black/60 rounded-lg mt-2 mb-4 mx-4">
		<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
	</nav>
{/if}
