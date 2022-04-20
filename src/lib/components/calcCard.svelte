<script>
	import Button from '$lib/components/button.svelte';

	let macros = {
		protein: '',
		carbs: '',
		fat: ''
	};
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
		weight: null,
		heightFt: null,
		heightIn: null,
		age: null,
		activity: '',
		goal: ''
	};
	// { name: 'Macro Calculator', gender: '', weight: '', heightFt: '', heightIn: '', age: '' },
	// ];

	function formulaM() {
		let weightKg = macro.weight * 0.453592;
		let heightCm = macro.heightFt * 30.48 + macro.heightIn * 2.54;
		let formulaM =
			10 * weightKg +
			6.25 * heightCm -
			5 * macro.age +
			5;

		return formulaM;
	}

	function calculate() {
		console.log({ macro });
		macros.protein = '220' + 'P';
		macros.carbs = '300' + 'C';
		macros.fat = '60' + 'F';
		console.log({ macros });

		let answer = formulaM();
		console.log(answer);

		// 10 x weight (kg) + 6.25 x height (cm) – 5 x age (y) + 5
	}
</script>

<section
	class="grid bg-black/50 mx-10 my-8 pb-2 rounded-lg outline outline-offset-2 outline-cyan-300"
>
	<h3 class="text-center mt-4 text-2xl font-bold">{macro.name}</h3>
	<form id="form" class="text-xl justify-items-center pt-4">
		<div class="div-calc">
			<label for="gender">Gender</label><br />
			<select bind:value={macro.gender} class="input-btn" id="gender" name="gender">
				<option value="male">Male</option>
				<option value="female">Female</option>
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
			<label for="heightF">Height (ft.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="heightF"
				name="heightF"
				bind:value={macro.heightFt}
				placeholder="Enter Height (ft.)"
			/>
		</div>
		<div class="div-calc">
			<label for="heightI">Height (in.)</label><br />
			<input
				class="input-btn"
				type="text"
				id="heightI"
				name="heightI"
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
		<div class="div-calc">
			<label for="activity">Activity</label><br />
			<select class="input-btn" id="activity" name="activity" bind:value={macro.activity}>
				<option value="sedentary">Sedentary (little to no exercise in a day)</option>
				<option value="slightly">Slightly Active (light exercise/sports 1-3 days/week)</option>
				<option value="moderately"
					>Moderately Active (moderate exercise/sports 3-5 days/week)</option
				>
				<option value="very">Very Active (hard exercise/sports 6-7 days a week)</option>
				<option value="extra"
					>Extra Active (very hard exercise/sports and physical job OR 2x training)</option
				>
			</select>
		</div>
		<div class="div-calc">
			<label for="goal">Goal</label><br />
			<select class="input-btn" id="goal" name="goal" bind:value={macro.goal}>
				<option value="rwl">Rapid Weight Loss (~2lb/week)</option>
				<option value="mwl">Moderate Weight Loss (~lb/week)</option>
				<option value="swl">Slow Weight Loss (~0.5lb/week)</option>
				<option value="mw">Maintain Weight (0lb/week)</option>
				<option value="slg">Slow Weight Gain (0.5% body weight/month)</option>
				<option value="mwg">Moderate Weight Gain (1% body weight/month)</option>
				<option value="rwg">Rapid Weight Gain (2% body weight/month)</option>
			</select>
		</div>
		<section class="text-center text-xl self-center">
			{macros.protein}
			{macros.carbs}
			{macros.fat}
		</section>
	</form>
	<Button on:click|once={calculate} let:calculate><p slot="calculate">{calculate}</p></Button>
</section>

<style>
	#form {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr 1fr;
	}

	input,
	select {
		/* text-align: center; */
		padding-left: 1rem;
	}
</style>
