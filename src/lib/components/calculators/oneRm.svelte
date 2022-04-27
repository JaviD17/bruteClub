<script>
	import Button from '$lib/components/button.svelte';

	let oneRm = null;

	let calcData = {
		name: 'One Rep Max Calculator',
		nRepMax: null
	};

	function formula() {
		calcData.nRepMax = parseInt(calcData.nRepMax);
		let upperOneRm = calcData.nRepMax * 1.1307 + 0.6998;
		upperOneRm = Math.floor(upperOneRm);

		return upperOneRm;
	}

	function calculate() {
		oneRm = formula();

		return oneRm;
	}

	// (4-to-6RM x 1.1307) + 0.6998 upper body
	// (4-to-6RM x 1.09703) + 14.2546 lower body
</script>

<section
	id="calc-card"
	class="flex flex-col justify-between bg-neutral-700 mx-10 my-8 pb-2 rounded-lg"
>
	<h3 class="text-center mt-4 text-2xl font-bold bg-neutral-900">{calcData.name}</h3>
	<form id="form" class="text-xl pt-4">
		<div class="div-calc">
			<label for="weight" class="label-btn">4-6 Rep Max</label><br />
			<input
				class="input-btn"
				size="20"
				type="text"
				id="weight"
				name="weight"
				bind:value={calcData.nRepMax}
				placeholder="Enter 4-6RM"
			/>
		</div>
	</form>
	{#if oneRm !== null}
		<section class="text-left text-xl self-center mt-2">
			<p>{oneRm}lbs 1RM</p>
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
