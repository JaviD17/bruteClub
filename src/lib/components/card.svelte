<script>
	import Button from '$lib/components/button.svelte';

	let newBlog = [
		{
			title: 'First Blog',
			date: 'April 15th, 2022',
			author: 'Javier Dominguez II'
		}
	];
</script>

<section id="card" class="w-full h-full p-8">
	<div id="inner-card" class="bg-black/40 p-px rounded-lg">
		{#if $$slots.info}
			{#each newBlog as { title, date, author }}
				<h2 class="m-4">{title}</h2>
				<slot name="info" {date} />
				<p class="m-4">{author}</p>
			{/each}
		{/if}
	</div>
</section>

<style>
	#inner-card {
		/* background-color: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)); */
        height: 24rem;
        width: 35rem;
	}
</style>
