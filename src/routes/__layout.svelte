<script>
	import '../app.css';
	import Footer from '$lib/layout/footer.svelte';
	import Header from '$lib/layout/header.svelte';
	import Profile from '$lib/layout/profile.svelte';

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section id="container">
	<Profile />
	<Header on:click={handleMessage} />

	<main id="main">
		<slot />
	</main>

	<Footer />
</section>

<style>
	#main {
		/* background-color: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)); */
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 7fr 3fr;
		grid-template-areas:
			'blog guides'
			'featured featured';
	}
	#container {
		display: grid;
		grid-template-columns: 2fr 18fr 1fr;
		grid-template-rows: 1fr 50px;
		grid-template-areas:
			'header main profile'
			'footer footer footer';
	}

	#main {
		grid-area: main;
	}
</style>
