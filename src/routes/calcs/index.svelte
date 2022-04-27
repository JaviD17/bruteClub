<script>
	import MacroCalc from '$lib/components/calculators/macro.svelte';
	import FfmiCalc from '$lib/components/calculators/ffmi.svelte';
	import OneRm from '$lib/components/calculators/oneRm.svelte';
</script>

<section class="headings">
	<h2 class="my-2 bg-neutral-900">Calculators</h2>
</section>


<section id="calc-section" class="xl:grid grid-cols-2 grid-rows-2 grid-flow-row-dense">
	<MacroCalc />
	<FfmiCalc />
	<OneRm />
</section>
