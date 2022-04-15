<script>
	import Button from '$lib/components/button.svelte';
</script>

<nav class="grid auto-rows-auto mt-14">
	<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
</nav>
