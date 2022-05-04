<script>
	import Button from '$lib/components/button.svelte';
	let newBlog = [
		{
			title: '8-16 Week Cut/Bulk',
			level: 'Beginner - Advanced',
			summary:
				'Get setup with a meal plan catered to you for an 8-16 week cut / bulk + unlimited questions with a 24hr response time including weekly macro adjustments.'
		},
		{
			title: '10 Week Powerbuilding',
			level: 'Intermediate - Advanced',
			summary:
			'Coached through a 10 week powerbuilding program for people wanting to increase functional strength and mobility through a strategic mixture of compound and isolation movements.'
		},
		{
			title: '16 Week Transformation',
			level: 'Intermediate - Advanced',
			summary:
				'Get setup with a meal plan catered to you for an 8 week cut / bulk + unlimited questions with a 24hr response time including weekly macro adjustments.'
		}
	];
</script>

{#if $$slots.info}
	{#each newBlog as { title, level, summary }}
		<a
			href="./blogs"
			class="grid bg-neutral-700 m-8 rounded-lg overflow-hidden text-neutral-100 shadow shadow-neutral-700"
		>
			<section id="details" class="text-base overflow-hidden text-center">
				<div class="p-px m-6">
					<h2
						class="p-2 text-3xl font-bold text-cyan-500 text-center border-4 border-neutral-900 rounded-lg"
					>
						{title}
					</h2>
				</div>

				<div>
					<p class="mx-6">{summary}</p>
				</div>

				<div class="self-end">
                    <slot name="info" {level} />
					<Button on:click
						><p class="inline font-bold" slot="services" let:serviceName>
							{serviceName}
						</p></Button
					>
				</div>
			</section>
		</a>
	{/each}
{/if}

<style>
    #details {
        display: grid;
    }
</style>
