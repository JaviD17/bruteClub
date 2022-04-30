<script>
	import Button from '$lib/components/button.svelte';

	let aboutData = {
		title: 'The Culture',
		content: ''
	};
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">About</h2>
</section>

<section id="coach-page" class="lg:grid grid-cols-3 2xl:grid-cols-4 justify-center">
	<!-- <CoachCard let:level
		><p slot="info" class="text-cyan-500 font-bold my-2">Level: {level}</p>
	</CoachCard> -->
	<!-- {#if $$slots.info} -->
		<a
			href="./blogs"
			class="grid bg-neutral-700 m-8 rounded-lg overflow-hidden text-neutral-100 shadow shadow-neutral-700"
		>
			<section id="details" class="text-base overflow-hidden text-center">
				<div class="p-px m-6">
					<h2
						class="p-2 text-3xl font-bold text-cyan-500 text-center border-4 border-neutral-900 rounded-lg"
					>
						{aboutData.title}
					</h2>
				</div>

				<!-- <div class="my-2 self-end">
					<p class="mx-6">{summary}</p>
					<slot name="info" {level} />
					<Button on:click
						><p class="inline font-bold" slot="services" let:serviceName>
							{serviceName}
						</p></Button
					>
				</div> -->
			</section>
		</a>
	<!-- {/if} -->
</section>

<!-- {#if $$slots.info}
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
</style> -->
