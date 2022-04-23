<script>
	import MacroCalc from '$lib/components/calculators/macro.svelte';
    import FfmiCalc from "$lib/components/calculators/ffmi.svelte";

</script>

<h2 class="text-center mt-14 mx-6 py-6 bg-black/50 rounded-lg text-4xl font-bold">Calculator Page</h2>

<section id="calc-section" class="lg:flex">
	<MacroCalc />
	<FfmiCalc />
</section>

<style>
    /* #calc-section {
        display: grid;
        grid-gap: 1rem;
    } */
</style>
