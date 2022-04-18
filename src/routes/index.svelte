<script>
	import Card from '$lib/components/card.svelte';
	export const title = 'Brute Club';
	import Button from '$lib/components/button.svelte';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section id="title" class="grid content-center text-6xl text-center mx-4 p-4 mt-16 text-gray-200 bg-black/70 rounded-lg">
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
</style>
