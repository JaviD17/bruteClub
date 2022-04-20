<script>
	import CalcCard from '$lib/components/calcCard.svelte';
</script>

<h2 class="text-center mt-14 mx-6 py-6 bg-black/50 rounded-lg text-4xl font-bold">Calculator Page</h2>

<section id="calc-section">
	<CalcCard />
	<CalcCard />
	<CalcCard />
</section>

<style>
    #calc-section {
        display: grid;
        grid-template-columns: 1fr 1fr;
        /* grid-template-rows: ; */
    }
</style>
