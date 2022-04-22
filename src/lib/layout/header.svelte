<script>
	import Logo from '$lib/layout/logo.svelte';
	import Nav from '$lib/layout/nav.svelte';
	
	let clicked = false;

	function handleClick() {
		clicked = !clicked;
		console.log(clicked);
	}
</script>

<header class="md:bg-black/50">
	<Logo on:click={handleClick} />
	<Nav on:click active={clicked} />
</header>

<style>
	header {
		/* background-image: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.25)); */
		grid-area: header;
	}
</style>
