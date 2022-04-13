<script>
	import '../app.css';
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
</script>

<section id="container" class="h-full grid grid-cols-10">
	<Header />

	<main class="col-span-9">
		<slot />
	</main>
</section>

<Footer />
