<script>
	import Card from '$lib/components/card.svelte';
	export const title = 'Brute Club';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section id="blog" class="bg-gray-700">
	<!-- <div class="bg-gray-200 grid m-40">
		<h1 class="text-center text-6xl">Your Darkness is your Development</h1>
	</div> -->
	<Card let:date><p slot="info">{date}</p></Card>
</section>

<section id="guides" class="bg-gray-400">
	<!-- <div class="bg-gray-200 grid m-40">
		<h1 class="text-center text-6xl">Your Darkness is your Development</h1>
	</div> -->
</section>

<section id="featured" class="bg-gray-900">
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
