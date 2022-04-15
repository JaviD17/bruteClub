<script>
	import Logo from '$lib/layout/logo.svelte';
	import Nav from '$lib/layout/nav.svelte';

	// function handleClick(e) {
	// 	console.log(e.path);
	// }
</script>

<header>
	<Logo />
	<Nav on:click />
</header>

<style>
	header {
		background-image: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.25));
		grid-area: header;
	}
</style>
