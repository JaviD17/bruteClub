<script>
	import Card from '$lib/card.svelte';
	export const title = 'Brute Club';

	let items = [
		{ title: '1st', name: 'Javi', content: 'some content' },
		{ title: '2nd', name: 'Dro', content: 'some content' },
		{ title: '3rd', name: 'Mando', content: 'some content' }
	];
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section id="hero" class="ml-14 pt-14">
	<div>
		<!-- <h1 class="text-center font-bold">Your Darkness is your Development</h1> -->
		<!-- {#each items as { title, name, content }} -->
		<Card>
			<h2 slot="title" let:title>{title}</h2>
			<section slot="names" let:names>
					{names}
			</section>
			<!-- <svelte:fragment slot="header">
					<h2>{title}</h2>
					<p>{name}</p>
					<p>{content}</p>
				</svelte:fragment> -->
		</Card>
		<!-- {/each} -->
	</div>
</section>
