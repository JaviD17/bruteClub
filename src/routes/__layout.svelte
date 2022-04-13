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

<section id="container" class="h-full grid grid-cols-10">
	<header class="col-span-1 text-xl">
		<Logo />
		<nav>
			<Profile />
			{#each links as link}
				<div class="text-left mx-3 mb-6 btns rounded-lg">
					<a class="rounded-lg p-1" href={link.href}>{link.name}</a>
				</div>
			{/each}
		</nav>
	</header>

	<main class="col-span-9">
		<slot />
	</main>
</section>

<footer class="flex justify-center items-center w-full h-16 absolute bottom-0">© 2022 Brute Club</footer>

<style>
	header {
		background-color: rgba(0, 0, 0, 0.4);
	}
</style>