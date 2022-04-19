<script>
    import Button from "$lib/components/button.svelte";
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
</script>

<section class="w-1/2 h-1/2 bg-black/50 m-4 rounded-lg">
    <form id="form" class="p-8">
        <div>
            <label for="gender">Gender</label><br />
            <input type="text" id="gender" name="gender" /><br />
        </div>
        <div>
            <label for="weight">Weight (lbs):</label><br />
            <input type="text" id="weight" name="weight" />
        </div>
    
        <div>
            <label for="gender">Height (ft)</label><br />
            <input type="text" id="gender" name="gender" /><br />
        </div>
        <div>
            <label for="weight">Height (in)</label><br />
            <input type="text" id="weight" name="weight" />
        </div>
        <div>
            <label for="weight">Age</label><br />
            <input type="text" id="weight" name="weight" />
        </div>
    </form>
    <!-- put button at bottom of form -->
</section>

<style>
	#form {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr 1fr;
	}
</style>
