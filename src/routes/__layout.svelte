<script>
	import '../app.css';
	import Footer from '$lib/layout/footer.svelte';
	import Header from '$lib/layout/header.svelte';
	import Profile from '$lib/layout/profile.svelte';

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section id="container" class="md:layout-container">
	<Profile />
	<Header on:click={handleMessage} />


	<main id="main">
		<slot />
	</main>

	<Footer />
</section>

<style>
	#container {
		/* grid-gap: 1rem; */
		grid-template-columns: 2fr 17.5fr 0.5fr;
		grid-template-rows: 1fr 50px;
		grid-template-areas:
			'header main profile'
			'header footer profile';
	}

	#main {
		grid-area: main;
	}
</style>
