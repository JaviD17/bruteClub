<script>
	import Button from '$lib/components/button.svelte';

	let aboutData = {
		title: 'The Culture',
		content:
			'At ODL we believe when science and the tools it offers is applied to training and nutrition can make things we do in every day life easier! The ability to perform compound movements with good mobility will allow us to live a pain free life.'
	};
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">About</h2>
</section>

<section class="lg:grid grid-cols-3 2xl:grid-cols-4 justify-center">
	<a
		href="./blogs"
		class="grid lg:col-start-2 2xl:col-start-2 2xl:col-end-4 bg-neutral-700 m-8 rounded-lg overflow-hidden text-neutral-100 shadow shadow-neutral-700"
	>
		<section id="details" class="text-base overflow-hidden text-center">
			<div class="p-px m-6">
				<h2
					class="p-2 text-3xl font-bold text-cyan-500 text-center border-4 border-neutral-900 rounded-lg"
				>
					{aboutData.title}
				</h2>
			</div>

			<div class="my-2 self-end">
				<p class="mx-6">{aboutData.content}</p>
				<!-- <slot name="info" {level} /> -->
				<Button on:click
					><p class="inline font-bold" slot="services" let:serviceName>
						{serviceName}
					</p></Button
				>
			</div>
		</section>
	</a>
</section>
