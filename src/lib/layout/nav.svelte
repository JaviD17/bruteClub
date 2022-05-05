<script>
	import Button from '$lib/components/button.svelte';
	import Profile from '$lib/layout/profile.svelte';

	let click = false;

	function handleClick() {
		click = !click;
	}
</script>

<nav class="hidden md:nav">
	<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
</nav>

<div id="menuIcon" class="m-4 md:hidden absolute">
	<svg
		on:click={handleClick}
		class="bg-neutral-700 rounded-lg shadow shadow-neutral-700"
		xmlns="http://www.w3.org/2000/svg"
		viewBox="-5 -7 24 24"
		width="60"
		fill="currentColor"
		><path
			d="M1 0h5a1 1 0 1 1 0 2H1a1 1 0 1 1 0-2zm7 8h5a1 1 0 0 1 0 2H8a1 1 0 1 1 0-2zM1 4h12a1 1 0 0 1 0 2H1a1 1 0 1 1 0-2z"
		/></svg
	>
	<!-- <Profile /> -->
</div>

{#if click}
	<nav class="nav-mobile md:hidden bg-neutral-900 rounded-lg mt-2 mb-4 mx-4">
		<Button on:click><p class="inline" slot="navLinks" let:navName>{navName}</p></Button>
	</nav>
{/if}

<style>
	#menuIcon {
		top: .5rem;
		left: .5rem;
	}
</style>
