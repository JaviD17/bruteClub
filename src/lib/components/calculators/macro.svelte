<script>
	import Button from '$lib/components/button.svelte';

	let macros = {
		calories: null,
		protein: null,
		carbs: null,
		fat: null
	};

	let calcData = {
		name: 'Macro Calculator',
		gender: '',
		weight: null,
		heightFt: null,
		heightIn: null,
		age: null,
		activity: null,
		goal: null
	};

	function formulaM() {
		let weightKg = calcData.weight * 0.453592;
		let heightCm = calcData.heightFt * 30.48 + calcData.heightIn * 2.54;
		let formulaM = 10 * weightKg + 6.25 * heightCm - 5 * calcData.age + 5;
		formulaM = formulaM * calcData.activity;
		formulaM = formulaM * calcData.goal;

		if (calcData.goal === '1') {
			return {
				calories: Math.floor(formulaM),
				protein: Math.floor((formulaM * 0.3) / 4),
				carbs: Math.floor((formulaM * 0.4) / 4),
				fat: Math.floor((formulaM * 0.3) / 9)
			};
		} else if (calcData.goal === '1.1' || calcData.goal === '1.2' || calcData.goal === '1.4') {
			return {
				calories: Math.floor(formulaM),
				protein: Math.floor((formulaM * 0.3) / 4),
				carbs: Math.floor((formulaM * 0.5) / 4),
				fat: Math.floor((formulaM * 0.2) / 9)
			};
		} else if (calcData.goal === '0.9' || calcData.goal === '0.8' || calcData.goal === '0.6') {
			return {
				calories: Math.floor(formulaM),
				protein: Math.floor((formulaM * 0.5) / 4),
				carbs: Math.floor((formulaM * 0.25) / 4),
				fat: Math.floor((formulaM * 0.25) / 9)
			};
		}
	}
	function formulaW() {
		let weightKg = calcData.weight * 0.453592;
		let heightCm = calcData.heightFt * 30.48 + calcData.heightIn * 2.54;
		let formulaW = 10 * weightKg + 6.25 * heightCm - 5 * calcData.age - 161;
		formulaW = formulaW * calcData.activity;
		formulaW = formulaW * calcData.goal;

		if (calcData.goal === '1') {
			return {
				calories: Math.floor(formulaW),
				protein: Math.floor((formulaW * 0.3) / 4),
				carbs: Math.floor((formulaW * 0.4) / 4),
				fat: Math.floor((formulaW * 0.3) / 9)
			};
		} else if (calcData.goal === '1.1' || calcData.goal === '1.2' || calcData.goal === '1.4') {
			return {
				calories: Math.floor(formulaW),
				protein: Math.floor((formulaW * 0.3) / 4),
				carbs: Math.floor((formulaW * 0.5) / 4),
				fat: Math.floor((formulaW * 0.2) / 9)
			};
		} else if (calcData.goal === '0.9' || calcData.goal === '0.8' || calcData.goal === '0.6') {
			return {
				calories: Math.floor(formulaW),
				protein: Math.floor((formulaW * 0.5) / 4),
				carbs: Math.floor((formulaW * 0.25) / 4),
				fat: Math.floor((formulaW * 0.25) / 9)
			};
		}
	}

	function calculate() {
		console.log({ calcData });
		if (calcData.gender == 'male') {
			let { calories, protein, carbs, fat } = formulaM();
			// console.log(protein, carbs, fat);
			macros.calories = calories;
			macros.protein = protein;
			macros.carbs = carbs;
			macros.fat = fat;
			console.log({ macros });
		} else if (calcData.gender == 'female') {
			let { calories, protein, carbs, fat } = formulaW();
			macros.calories = calories;
			macros.protein = protein;
			macros.carbs = carbs;
			macros.fat = fat;
			console.log({ macros });
		}
	}
</script>

<section
	id="calc-card"
	class="row-span-2 flex flex-col justify-between bg-black/80 mx-10 my-8 pb-2 rounded-lg outline outline-offset-2 outline-cyan-300"
>
	<h3 class="text-center mt-4 text-2xl font-bold">{calcData.name}</h3>
	<form id="form" class="text-xl pt-4">
		<div class="div-calc">
			<label for="gender" class="label-btn">Gender</label><br />
			<select bind:value={calcData.gender} class="input-btn" id="gender" name="gender">
				<option value="" />
				<option value="male">Male</option>
				<option value="female">Female</option>
			</select>
		</div>
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
			<label for="age" class="label-btn">Age</label><br />
			<input
				class="input-btn"
				type="text"
				id="age"
				name="age"
				bind:value={calcData.age}
				placeholder="Enter Age"
			/>
		</div>
		<div class="">
			<label for="activity" class="label-btn">Activity</label><br />
			<select class="input-btn" id="activity" name="activity" bind:value={calcData.activity}>
				<option value="1.15">Sedentary (little to no exercise)</option>
				<option value="1.3">Slightly Active (exercise/sports 1-3 hrs/week)</option>
				<option value="1.50">Moderately Active (exercise/sports 4-6 hrs/week)</option>
				<option value="1.7">Very Active (exercise/sports 7-9 hrs/week)</option>
				<option value="1.9">Extra Active (exercise/sports 10+ hrs/week)</option>
			</select>
		</div>
		<div class="">
			<label for="goal" class="label-btn">Goal</label><br />
			<select class="input-btn" id="goal" name="goal" bind:value={calcData.goal}>
				<option value="0.6">Rapid Weight Loss (~2lb/week)</option>
				<option value="0.8">Moderate Weight Loss (~lb/week)</option>
				<option value="0.9">Slow Weight Loss (~0.5lb/week)</option>
				<option value="1">Maintain Weight (0lb/week)</option>
				<option value="1.1">Slow Weight Gain (0.5% body weight/month)</option>
				<option value="1.2">Moderate Weight Gain (1% body weight/month)</option>
				<option value="1.4">Rapid Weight Gain (2% body weight/month)</option>
			</select>
		</div>
	</form>
	{#if macros.calories !== null}
		<section class="text-left text-xl self-center mt-2">
			<p>{macros.calories} Calories (TDEE)</p>
			<p>{macros.protein}g Protein</p>
			<p>{macros.carbs}g Carbs</p>
			<p>{macros.fat}g Fat</p>
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
