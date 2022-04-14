<script>
	import Button from '$lib/button/button.svelte';
	let clicked = false;

	let links = [
		{ name: 'Profile', href: '/profile' },
		{ name: 'Subscriptions', href: '/profile/subscriptions' },
		{ name: 'Settings', href: '/profile/settings' }
	];
</script>

<section id="profile" class="mt-2.5 relative right top-0">
	<Button on:message>
		<svelte:fragment slot="btn">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="-2 -2 24 24" width="60" fill="currentColor"
				><path
					d="M10 20C4.477 20 0 15.523 0 10S4.477 0 10 0s10 4.477 10 10-4.477 10-10 10zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm0-14a4 4 0 0 1 4 4v2a4 4 0 1 1-8 0V8a4 4 0 0 1 4-4zm0 2a2 2 0 0 0-2 2v2a2 2 0 1 0 4 0V8a2 2 0 0 0-2-2zM5.91 16.876a8.033 8.033 0 0 1-1.58-1.232 5.57 5.57 0 0 1 2.204-1.574 1 1 0 1 1 .733 1.86c-.532.21-.993.538-1.358.946zm8.144.022a3.652 3.652 0 0 0-1.41-.964 1 1 0 1 1 .712-1.868 5.65 5.65 0 0 1 2.284 1.607 8.032 8.032 0 0 1-1.586 1.225z"
				/>
			</svg>
		</svelte:fragment>
	</Button>
</section>

{#if clicked}
	<section id="submenu" class="absolute top-0 ml-36 mt-24 rounded-lg">
		{#each links as link}
			<div class="rounded m-2 btns text-lg">
				<a class="mx-2" href={link.href}>{link.name}</a>
			</div>
		{/each}
	</section>
{/if}

<style>
	#profile {
		grid-area: profile;
	}
	#submenu {
		background-color: rgba(0, 0, 0, 0.5);
	}
</style>
