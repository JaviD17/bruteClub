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

<header class="flex justify-between bg-gray-900 w-full h-16">
	<Logo />
	<nav class="flex justify-evenly items-center w-11/12">
		{#each links as link}
			<div class="ml-2.5 p-1 rounded-lg hover:bg-gray-800">
				<a href={link.href}>{link.name}</a>
			</div>
		{/each}
	</nav>
	<Profile />
</header>

<main>
	<slot />
</main>

<footer class="flex justify-center items-center bg-gray-900 w-full h-16">
	© 2022 Brute Club
</footer>
