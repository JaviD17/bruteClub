<script>
	import Button from '$lib/components/button.svelte';
	// All Calcs
	// Macro Calc
	// FFMI Calc
	// 1RM Calc
	// Body fat chart

	// conversion calculators

	// lbs to kg
	// ft to cm

	// macro calculator

	// input for gender
	// input for weight (lbs)
	// height ft
	// height in
	// age

	// let gender;
	// let weight = '';
	// let fHeight = '';
	// let iHeight = '';
	// let age = '';

	// let calcData = [
	let macro = {
		name: 'Macro Calculator',
		gender: '',
		weight: '',
		heightFt: '',
		heightIn: '',
		age: ''
	};
	// { name: 'Macro Calculator', gender: '', weight: '', heightFt: '', heightIn: '', age: '' },
	// ];

	function calculate() {
		console.log({macro});
	}
</script>

<section
	class="grid bg-black/50 mx-10 my-8 pb-2 rounded-lg outline outline-offset-2 outline-cyan-300"
>
	<form id="form" class="text-xl justify-items-center pt-4">
		<div class="div-calc">
			<label for="gender">Gender</label><br />
			<select bind:value={macro.gender} class="input-btn" id="gender">
				<option value="Male">Male</option>
				<option value="Femle">Female</option>
			</select>
		</div>
		<div class="div-calc">
			<label for="weight">Weight (lbs.)</label><br />
			<input
				class="input-btn"
				size="20"
				type="text"
				id="weight"
				name="weight"
				bind:value={macro.weight}
				placeholder="Enter Weight (lbs)"
			/>
		</div>

		<div class="div-calc">
			<label for="fheight">Height (ft.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="fheight"
				name="fheight"
				bind:value={macro.heightFt}
				placeholder="Enter Height (ft.)"
			/>
		</div>
		<div class="div-calc">
			<label for="iheight">Height (in.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="iheight"
				name="iheight"
				bind:value={macro.heightIn}
				placeholder="Enter Height (in.)"
			/>
		</div>
		<div class="div-calc">
			<label for="age">Age</label><br />
			<input
				class="input-btn"
				type="text"
				id="age"
				name="age"
				bind:value={macro.age}
				placeholder="Enter Age"
			/>
		</div>
	</form>
	<Button on:click={calculate} let:calculate><p slot="calculate">{calculate}</p></Button>
</section>

<style>
	#form {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr 1fr;
	}

	input,
	select {
		color: #111827;
		/* text-align: center; */
		padding-left: 1rem;
	}
</style>
