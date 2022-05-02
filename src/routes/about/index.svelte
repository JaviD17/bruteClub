<script>
	import Button from '$lib/components/button.svelte';

	let aboutData = {
		title: 'The Culture',
		content: 'We are no more than beings with aim. Here at ODL.'
	};
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">About</h2>
</section>

<section class="lg:grid grid-cols-3 2xl:grid-cols-4 justify-center">
	<!-- <CoachCard let:level
		><p slot="info" class="text-cyan-500 font-bold my-2">Level: {level}</p>
	</CoachCard> -->
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
</section>

