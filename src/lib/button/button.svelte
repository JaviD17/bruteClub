<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function handleClick() {
		dispatch('message', {
			text: 'clicked'
		});
	}
</script>

<button
	on:click={handleClick}
	class="text-2xl bg-gray-500 hover:bg-transparent p-0.5 m-2 rounded-full ease-in-out duration-400 hover:outline outline-offset-1 outline-4 outline-purple-600 hover:text-gray-100"
>
	<slot name="btn">fallbacks</slot>
</button>
