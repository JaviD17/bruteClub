<script>
	import CoachCard from '$lib/components/coachCard.svelte';
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">Coaches</h2>
</section>

<section id="coach-page" class="lg:grid grid-cols-3 2xl:grid-cols-4">
	<CoachCard let:level
		><p slot="info" class="text-cyan-500 font-bold my-2">Level: {level}</p>
	</CoachCard>
</section>

<!-- main-card lg:grid grid-cols-3 2xl:grid-cols-4 -->

<!-- <section id="blog-page" class="lg:grid grid-cols-3 2xl:grid-cols-4">
    <Card let:date><p class="" slot="info">Date: {date}</p></Card>
</section> -->
