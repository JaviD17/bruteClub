<script>
	import Card from '$lib/components/blogCard.svelte';
	import Button from '$lib/components/button.svelte';
	import CoachCard from '$lib/components/coachCard.svelte';

	export const title = 'Obsessed Demon Labz';
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<!-- 		class="col-span-3 2xl:col-span-4 text-6xl text-center mx-6 md:mt-16 text-neutral-100 bg-neutral-700 rounded-xl shadow shadow-neutral-700"
 -->

<section class="main-card lg:grid grid-cols-3 2xl:grid-cols-4">
	<section
		id="title"
		class="col-span-3 2xl:col-span-4 grid grid-cols-3 content-center text-6xl text-center m-6 text-neutral-100 bg-neutral-700 rounded-xl shadow shadow-neutral-700"
	>
		<h1 class="font-bold bg-neutral-900 my-4 col-span-3">Obsessed Demon Labz</h1>
		<!-- <p class="text-xl">O.D.L.</p> -->
		<!-- <p class="text-xl">Commitment = Doing what is REQUIRED</p> -->
	</section>

	<section id="hero" class="lg:col-span-3 2xl:col-span-4 lg:grid grid-cols-4 mx-6 rounded-lg">
		<img src='./heroBanner.png' alt='hero' class="col-start-2 col-end-4 object-cover">
		<Button><p slot="calcs" let:calcName>{calcName}</p></Button>
	</section>

	<section
		class="col-span-3 2xl:col-span-4 grid grid-cols-3 content-center text-5xl text-center m-6 text-neutral-100 bg-neutral-700 rounded-xl shadow shadow-neutral-700"
	>
		<h2 class="font-bold bg-neutral-900 my-4 col-span-3">Coaching</h2>
	</section>

	<CoachCard let:level
		><p slot="info" class="text-cyan-500 font-bold my-2">Level: {level}</p>
	</CoachCard>

	<section
		class="col-span-3 2xl:col-span-4 grid grid-cols-3 content-center text-5xl text-center m-6 text-neutral-100 bg-neutral-700 rounded-xl"
	>
		<h2 class="font-bold bg-neutral-900 my-4 col-span-3">Blog</h2>
		<!-- <Button><p slot="calcs" let:calcName>{calcName}</p></Button> -->
	</section>

	<Card let:date><p class="" slot="info">Date: {date}</p></Card>
</section>
