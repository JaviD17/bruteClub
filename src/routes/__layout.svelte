<script>
	import '../app.css';
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
</script>

<section id="container" class="w-full h-full bg-cover">
	<Header />

	<main id="main">
		<slot />
	</main>

	<Footer />

</section>


<style>
	#container {
		background-image: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)), url('./hero.jpg');
		display: grid;
		grid-template-columns: 125px 1fr;
		grid-template-rows: 1fr 50px;
		grid-template-areas: 
		"header main"
		"footer footer";
	}

	#main {
		grid-area: main;
	}
</style>
