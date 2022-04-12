<script>
	import '../app.css';
	import Logo from '$lib/logo.svelte';
	import Profile from '$lib/profile.svelte';

	let links = [
		{ name: 'Blog', href: '/blogs' },
		{ name: 'Calculators', href: '/calculators' },
		{ name: 'About', href: '/about' },
		{ name: 'Coaching', href: '/coaching' }
	];
</script>

<header class="flex justify-start bg-slate-800 w-full h-16">
	<Logo />
	<nav class="flex justify-evenly text-gray-200 items-center w-6/12">
		{#each links as link}
			<div class="ml-2.5 p-1 rounded-lg hover:bg-slate-900">
				<a href={link.href}>{link.name}</a>
			</div>
		{/each}
	</nav>
	<Profile />
</header>

<main>
	<slot />
</main>

<footer class="flex justify-center">© 2022 Brute Club</footer>
