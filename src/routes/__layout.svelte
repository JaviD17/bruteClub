<script>
	import '../app.css';
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
</script>

<section id="container" class="h-full grid grid-cols-12">
	<Header />

	<main class="col-span-11">
		<slot />
	</main>
</section>

<Footer />
