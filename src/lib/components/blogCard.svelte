<script>
	import Button from '$lib/components/button.svelte';
	let newBlog = [
		{
			title: 'How to Cut',
			date: 'April 15th, 2022',
			author: 'Javier Dominguez II',
			summary: 'Using science is the most effective way to cut in 2022. Click this to learn!'
		},
		{
			title: 'How to Maintain',
			date: 'April 16th, 2022',
			author: 'Javier Dominguez II',
			summary: 'Using science is the most effective way to maintain in 2022. Click this to learn!'
		},
		{
			title: 'How to Maintain',
			date: 'April 16th, 2022',
			author: 'Javier Dominguez II',
			summary: 'Using science is the most effective way to maintain in 2022. Click this to learn!'
		}
	];
</script>

{#if $$slots.info}
	{#each newBlog as { title, date, author, summary }}
		<a
			id="inner-card-a"
			href="./blogs"
			class="bg-neutral-700 m-8 rounded-lg overflow-hidden text-neutral-100 shadow shadow-neutral-600"
		>
			<div id="card-img">
				<img
					src="./blog1.jpg"
					alt="man prepping food"
					class="rounded-lg object-cover object-center"
					id="card-img"
				/>
			</div>
			<div id="card-details" class="text-base">
				<div id="details-content" class="p-px mx-6 mt-4">
					<p>{summary}</p>
				</div>
				<div id="details-by" class="mx-6 border-t-2 border-neutral-100">
					<h2 class="mt-2 text-3xl font-bold text-cyan-500">{title}</h2>
					<slot name="info" {date} />
					<p>By: {author}</p>
				</div>
				<Button on:click
					><p id="button" class="font-bold" slot="blog" let:blogName>{blogName}</p></Button
				>
			</div>
		</a>
	{/each}
{/if}

<style>
	#button {
		grid-area: 'button';
	}
	#card-img {
		grid-area: 'card-img';
	}
	#details-content {
		grid-area: 'details-content';
	}
	#details-by {
		grid-area: 'details-by';
	}
	#card-details {
		grid-area: 'card-details';
		display: grid;
		grid-template-rows: 1fr 1fr 0.5fr;
		grid-template-areas:
			'details-content'
			'details-by'
			'button';
	}
	#inner-card-a {
		display: grid;
	}
</style>
