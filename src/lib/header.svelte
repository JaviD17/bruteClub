<script>
	import Logo from '$lib/logo.svelte';
	import Nav from '$lib/nav.svelte';
</script>

<header class="text-xl">
	<Logo />
	<Nav />
</header>

<style>
	header {
		background-color: rgba(0, 0, 0, 0.4);
		grid-area: header;
	}
</style>