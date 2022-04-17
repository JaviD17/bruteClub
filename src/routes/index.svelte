<script>
	import Card from '$lib/components/card.svelte';
	export const title = 'Brute Club';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

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
