<script>
	import Logo from '$lib/layout/logo.svelte';
	import Nav from '$lib/layout/nav.svelte';
</script>

<header class="text-xl">
	<Logo />
	<Nav on:click/>
</header>

<style>
	header {
		background-image: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.25));
		grid-area: header;
	}
</style>
