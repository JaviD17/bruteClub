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
	<div id="inner-card" class="bg-black/25 p-px rounded-lg text-center h-48 w-48">
		{#if $$slots.info}
			{#each newBlog as { title, date, author }}
				<div class="p-4"><img src="./blog1.jpg" alt="man prepping food" class="rounded-lg h-36 object-cover object-right-bottom" id="card-img"/></div>
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
    #card-img {
        width: 34rem;
    }
</style>
