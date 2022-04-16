<script>
	let newBlog = [
		{
			title: 'First Blog',
			date: 'April 15th, 2022',
			author: 'Javier Dominguez II'
		}
	];
</script>

<a id="inner-card-a" href="./blogs" class="bg-black/25 my-2 rounded-lg overflow-hidden">
	{#if $$slots.info}
		{#each newBlog as { title, date, author }}
			<div id="card-img">
				<img
					src="./blog1.jpg"
					alt="man prepping food"
					class="rounded-lg object-cover object-center h-full"
					id="card-img"
				/>
			</div>
			<div id="card-details" class="text-xs m-4">
				<div id="details-content" class="">
                    <p>content inside</p>
                </div>
				<div id="details-by">
					<h2 class="text-sm">{title}</h2>
					<slot name="info" {date} />
					<p>{author}</p>
				</div>
			</div>
		{/each}
	{/if}
</a>

<style>
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
        grid-template-rows: 2fr 1fr;
        grid-template-areas: 
        'details-content'
        'details-by';
	}
	#inner-card-a {
		display: grid;
		grid-template-columns: 1fr 3fr;
		grid-template-areas: 'card-img card-content';
	}
</style>
