<script>
	// import { createEventDispatcher } from 'svelte';

	// const dispatch = createEventDispatcher();

	// function handleClick() {
	// 	dispatch('message', {
	// 		text: 'clicked'
	// 	});
	// }

</script>

<button
	on:click
	class="justify-self-evenly text-xl font-bold bg-gray-900/20 hover:bg-gray-100/75 p-1.5 m-2 rounded-full ease-in-out duration-400 hover:outline outline-offset-2 outline-2 outline-cyan-300 hover:text-gray-900"
>
	{#if $$slots.header}
		<slot name="header" />
	{/if}
</button>
