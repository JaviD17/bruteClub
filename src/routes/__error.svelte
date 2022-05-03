<script context="module">
	export function load({ error }) {
		return {
			props: { message: error.message }
		};
	}
</script>

<script>
    export let message
    import Button from "$lib/components/button.svelte";
</script>

<div class="error my-20 mx-20 text-4xl font-bold bg-neutral-700 rounded-lg text-center p-10">
	<h2>Oops</h2>
    <p>Following Page {message}</p>
    <Button let:errorName><p slot="error">{errorName}</p></Button>
</div>

<style>

</style>
