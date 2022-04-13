<script>
	import Profile from '$lib/profile.svelte';

	let links = [
		{ name: 'Blog', href: '/blogs' },
		{ name: 'Calcs', href: '/calcs' },
		{ name: 'About', href: '/about' },
		{ name: 'Coaches', href: '/coaches' }
	];
</script>

<nav>
	<Profile />
	{#each links as link}
		<div class="text-left mx-3 mb-6 btns rounded-lg">
			<a class="rounded-lg p-1" href={link.href}>{link.name}</a>
		</div>
	{/each}
</nav>
