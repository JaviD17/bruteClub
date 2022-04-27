<script>
	import Button from '$lib/components/button.svelte';

	let macros = {
		normalizedFfmi: null,
		ffmi: null,
		fatFreeMass: null
	};

	let calcData = {
		name: 'FFMI Calculator',
		weight: null,
		heightFt: null,
		heightIn: null,
		bodyFat: null
	};

	function formula() {
		let heightF = parseInt(calcData.heightFt);
		let heightI = parseInt(calcData.heightIn);
		let bodyFat = parseInt(calcData.bodyFat);
		let weight = parseInt(calcData.weight);

		let heightTotal = (heightF * 12 + heightI) * 0.0254;
		let bodyFatPercent = bodyFat / 100;
		let leanWeight = weight * (1 - bodyFatPercent);
		let ffmi = leanWeight / 2.2 / Math.pow(heightTotal, 2);
		let normalizedFfmi = ffmi + 6.3 * (1.8 - heightTotal);

		normalizedFfmi = Math.round((normalizedFfmi + Number.EPSILON) * 100) / 100;

		ffmi = Math.round((ffmi + Number.EPSILON) * 100) / 100;

		return {
			normalizedFfmi: normalizedFfmi,
			ffmi: ffmi,
			fatFreeMass: ffmi
		};
	}

	function calculate() {
		let { normalizedFfmi, ffmi, fatFreeMass } = formula();
		macros.normalizedFfmi = normalizedFfmi;
		macros.ffmi = ffmi;
		macros.fatFreeMass = fatFreeMass;
	}
</script>

<section
	id="calc-card"
	class="flex flex-col justify-between bg-neutral-700 mx-10 my-8 pb-2 rounded-lg"
>
	<h3 class="text-center mt-4 text-2xl font-bold bg-neutral-900">{calcData.name}</h3>
	<form id="form" class="text-xl pt-4">
		<div class="div-calc">
			<label for="weight" class="label-btn">Weight (lbs.)</label><br />
			<input
				class="input-btn"
				size="20"
				type="text"
				id="weight"
				name="weight"
				bind:value={calcData.weight}
				placeholder="Enter Weight (lbs)"
			/>
		</div>

		<div class="div-calc">
			<label for="heightF" class="label-btn">Height (ft.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="heightF"
				name="heightF"
				bind:value={calcData.heightFt}
				placeholder="Enter Height (ft.)"
			/>
		</div>
		<div class="div-calc">
			<label for="heightI" class="label-btn">Height (in.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="heightI"
				name="heightI"
				bind:value={calcData.heightIn}
				placeholder="Enter Height (in.)"
			/>
		</div>
		<div class="div-calc">
			<label for="bodyFat" class="label-btn">Body Fat %</label><br />
			<input
				class="input-btn"
				type="text"
				id="bodyFat"
				name="bodyFat"
				bind:value={calcData.bodyFat}
				placeholder="Enter Body Fat %"
			/>
		</div>
	</form>
	{#if macros.normalizedFfmi !== null}
		<section class="text-left text-xl self-center mt-2">
			<p>{macros.normalizedFfmi} Normalized FFMI</p>
			<p>{macros.ffmi} FFMI</p>
			<p>{macros.fatFreeMass} Fat-Free Mass</p>
		</section>
	{/if}
	<Button on:click|once={calculate} let:calculate><p slot="calculate">{calculate}</p></Button>
</section>

<style>
	#form {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		/* grid-gap: 1rem; */
		/* grid-template-columns: 1fr 1fr 1fr;
		grid-template-rows: 1fr 1fr; */
	}
</style>
