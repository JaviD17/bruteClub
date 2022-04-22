<script>
	import Button from '$lib/components/button.svelte';

	export let active;
</script>

<nav class="nav hidden md:block">
	<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
</nav>

{#if active}
	<nav class="nav-mobile md:nav md:hidden">
		<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
	</nav>
{/if}
