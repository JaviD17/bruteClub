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

<!-- <header class="flex justify-between bg-gray-900 w-full h-16">
	<Logo />
	<nav class="flex justify-evenly items-center w-11/12">
		{#each links as link}
			<div class="ml-2.5 p-1 rounded-lg hover:bg-gray-800">
				<a href={link.href}>{link.name}</a>
			</div>
		{/each}
	</nav>
	<Profile />
</header> -->

<section id="container" class="h-full grid grid-cols-12">
	<header class="col-span-1">
		<Logo />
		<Profile />
		<nav>
			{#each links as link}
				<div class="ml-2.5 p-1 rounded-lg hover:bg-gray-800">
					<a href={link.href}>{link.name}</a>
				</div>
			{/each}
		</nav>
	</header>

	<main class="col-span-11">
		<slot />
	</main>
</section>

<footer class="flex justify-center items-center w-full h-16 absolute bottom-0">© 2022 Brute Club</footer>
