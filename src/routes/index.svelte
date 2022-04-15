<script>
	import Button from '$lib/button/button.svelte';
	export const title = 'Brute Club';

	let items = [
		{ title: '1st', name: 'Javi', content: 'some content' },
		{ title: '2nd', name: 'Dro', content: 'some content' },
		{ title: '3rd', name: 'Mando', content: 'some content' }
	];

	function handleMessage(event) {
		alert(event.detail.text);
	}
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<section id="hero" class="ml-14 pt-14">
	<div class="m-40">
		<h1 class="text-center font-bold text-6xl">Your Darkness is your Development</h1>
		<Button on:message={handleMessage}>
			<p slot="btn">Click Me</p>
		</Button>
	</div>
</section>
