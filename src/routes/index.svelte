<script>
	import Card from '$lib/components/card.svelte';
	export const title = 'Brute Club';
	import Button from '$lib/components/button.svelte';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section class="main-card">
	<section
		id="title"
		class="grid content-center text-6xl text-center mx-4 p-4 md:mt-16 text-gray-200 bg-black/70 rounded-lg"
	>
		<h1 class="font-bold">Brute Club</h1>
		<p class="text-xl">Your Darkness is Your Development</p>
		<Button><p slot="calcs" let:calcName>{calcName}</p></Button>
	</section>

	<section id="blog" class="">
		<!-- <div class="bg-gray-200 grid m-40">
		<h1 class="text-center text-6xl">Your Darkness is your Development</h1>
	</div> -->
		<Card let:date><p class="" slot="info">Date: {date}</p></Card>
	</section>

	<section id="guides" class="">
		<Card let:date><p class="" slot="info">Date: {date}</p></Card>

		<!-- <div class="bg-gray-200 grid m-40">
		<h1 class="text-center text-6xl">Your Darkness is your Development</h1>
	</div> -->
	</section>

	<section id="featured" class="">
		<Card let:date><p class="" slot="info">Date: {date}</p></Card>

		<!-- <div class="bg-gray-200 grid m-40">
		<h1 class="text-center text-6xl">Your Darkness is your Development</h1>
	</div> -->
	</section>
</section>


<style>
	#title {
		grid-area: title;
	}
	#blog {
		grid-area: blog;
	}
	#guides {
		grid-area: guides;
	}
	#featured {
		grid-area: featured;
	}
	@media (min-width: 1280px) {
		.main-card {
			/* background-color: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)); */
			display: grid;
			grid-gap: 1rem;
			grid-template-columns: 1fr 1fr;
			grid-template-rows: 0.5fr 1fr 1fr;
			grid-template-areas:
				'title title'
				'featured featured'
				'blog guides';
			/* grid-template-areas:
			'blog guides'
			'featured featured'; */
		}
	}

</style>
