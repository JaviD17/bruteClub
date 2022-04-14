<script>
	import '../app.css';
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
	import Profile from '$lib/profile.svelte';

	function handleMessage(event) {
		alert(event.detail.text);
	}
</script>

<section id="container" class="w-full h-full bg-cover">
	<Profile on:message={handleMessage} />
	<Header on:message={handleMessage}/>

	<main id="main">
		<slot />
	</main>

	<Footer />

</section>


<style>
	#container {
		background-image: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)), url('./hero.jpg');
		display: grid;
		grid-template-columns: 125px 1fr 90px;
		grid-template-rows: 1fr 50px;
		grid-template-areas: 
		"header main profile"
		"footer footer footer";
	}

	#main {
		grid-area: main;
	}
</style>
