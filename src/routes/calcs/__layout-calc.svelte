<script>
	// import '../app.css';
	import Footer from '$lib/layout/footer.svelte';
	import Header from '$lib/layout/header.svelte';
	import Profile from '$lib/layout/profile.svelte';

	function handleMessage(event) {
		console.log(event);
	}
</script>

<section id="container">
	<main>
		<slot />
	</main>
</section>
