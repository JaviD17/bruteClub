<script>
	import Logo from '$lib/layout/logo.svelte';
	import Nav from '$lib/layout/nav.svelte';
	
	let clicked = false;

	function handleClick() {
		clicked = !clicked;
		console.log(clicked);
	}
</script>

<header class="md:bg-neutral-800">
	<Logo on:click={handleClick} />
	<Nav on:click active={clicked} />
</header>

<style>
	header {
		grid-area: header;
	}
</style>
