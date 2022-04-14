<script>
	// import Profile from '$lib/profile.svelte';
	import Button from '$lib/button/button.svelte';

	let links = [
		{ name: 'Blog', href: '/blogs' },
		{ name: 'Calcs', href: '/calcs' },
		{ name: 'About', href: '/about' },
		{ name: 'Coaches', href: '/coaches' }
	];


</script>

<nav class="grid auto-rows-auto mt-14 text-2xl">
	{#each links as link}
		<Button on:message>
			<a slot="btn" href={link.href}>{link.name}</a>
		</Button>
	{/each}
</nav>
