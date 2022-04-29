<script>
	import Button from '$lib/components/button.svelte';
	let newBlog = [
		{
			title: '8-12 Week Cut/Bulk',
			level: 'Beginner - Advanced',
			summary:
				'Get setup with a meal plan catered to you for an 8 week cut / bulk + unlimited questions with a 24hr response time including weekly macro adjustments.'
		},
		{
			title: '10 Week Powerbuilding Plan',
			level: 'Intermediate - Advanced',
			summary:
				'Get setup with a plan catered to you for an 8 week cut / bulk + unlimited questions with a 24hr response time including weekly macro adjustments.'
		},
		{
			title: '16 Week Transformation',
			level: 'Advanced',
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

				<div class="my-2 self-end">
					<p class="mx-6">{summary}</p>
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
