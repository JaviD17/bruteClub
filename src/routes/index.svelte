<script>
	import Card from '$lib/components/card.svelte';
	export const title = 'DS17';
	import Button from '$lib/components/button.svelte';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section class="main-card lg:grid grid-cols-3 2xl:grid-cols-4">
	<section
		id="title"
		class="col-span-3 2xl:col-span-4 grid content-center text-6xl text-center mx-6 md:mt-16 text-neutral-100 bg-neutral-700 rounded-xl"
	>
		<h1 class="font-bold">DS17</h1>
		<p class="text-xl">Easy Choices -> Hard Life</p>
		<p class="text-xl">Hard Choices -> Easy Life</p>
		<Button><p slot="calcs" let:calcName>{calcName}</p></Button>
	</section>

	<section
		class="col-span-3 2xl:col-span-4 grid content-center text-6xl text-center m-6 text-neutral-100 bg-neutral-700 rounded-xl"
	>
		<h2 class="font-bold">DS17</h2>
		<p class="text-xl">Easy Choices -> Hard Life</p>
		<p class="text-xl">Hard Choices -> Easy Life</p>
		<Button><p slot="calcs" let:calcName>{calcName}</p></Button>
	</section>

	<Card let:date><p class="" slot="info">Date: {date}</p></Card>
</section>
