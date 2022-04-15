<script>
	import Button from '$lib/button/button.svelte';

	let clicked = false;
	let hovering;

	let links = [
		{ name: 'Profile', href: '/profile' },
		{ name: 'Subscriptions', href: '/profile/subscriptions' },
		{ name: 'Settings', href: '/profile/pro-settings' }
	];

	function enter() {
		hovering = true;
	}
	function leave() {
		hovering = false;
	}
</script>

<section on:mouseenter={enter} on:mouseleave={leave} id="profile" class="grid self-start">
	<!-- second on:click is a shorthand to forward events -->
	<Button on:click>
		<svelte:fragment slot="header">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="-2 -2 24 24" width="50" fill="currentColor"
				><path
					d="M10 20C4.477 20 0 15.523 0 10S4.477 0 10 0s10 4.477 10 10-4.477 10-10 10zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm0-14a4 4 0 0 1 4 4v2a4 4 0 1 1-8 0V8a4 4 0 0 1 4-4zm0 2a2 2 0 0 0-2 2v2a2 2 0 1 0 4 0V8a2 2 0 0 0-2-2zM5.91 16.876a8.033 8.033 0 0 1-1.58-1.232 5.57 5.57 0 0 1 2.204-1.574 1 1 0 1 1 .733 1.86c-.532.21-.993.538-1.358.946zm8.144.022a3.652 3.652 0 0 0-1.41-.964 1 1 0 1 1 .712-1.868 5.65 5.65 0 0 1 2.284 1.607 8.032 8.032 0 0 1-1.586 1.225z"
				/>
			</svg>
		</svelte:fragment>
	</Button>

	{#if hovering}
		<section id="submenu" class="absolute right right-0 mt-20 mr-4 rounded-lg grid">
			{#each links as link}
				<Button on:click>
					<a slot="header" class="mx-2" href={link.href}>{link.name}</a>
				</Button>
			{/each}
		</section>
	{/if}
</section>

<style>
	#profile {
		grid-area: profile;
	}
	#submenu {
		background-image: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.25));
	}
</style>
