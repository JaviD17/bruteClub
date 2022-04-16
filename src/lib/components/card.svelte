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

<section id="card" class="w-full h-full">
	{#if $$slots.info}
		{#each newBlog as {title, date, author}}
            <h2>{title}</h2>
			<slot name="info" {date} />
            <p>{author}</p>
		{/each}
	{/if}
	<!-- <h2>hey</h2>
    <p>Date</p>
    <p>Author</p> -->
</section>

<style>
	#card {
		background-color: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5));
	}
</style>
