<script>
	import Button from '$lib/components/button.svelte';
	let logIn = true;
	let loggedIn = false;

	function handleLogIn() {
		logIn = !logIn;
	}
</script>

<section id="profilePage" class="xl:grid xl:grid-cols-5 2xl:grid-cols-3">
	<section class="headings xl:col-span-5 2xl:grid-cols-3">
		<h2 class="my-2 bg-neutral-900">Profile</h2>
	</section>

	{#if !loggedIn}
		<section
			id="logIn"
			class="bg-neutral-700 my-10 mx-10 xl:mx-0 rounded-lg text-center xl:col-start-2 xl:col-end-5 2xl:col-start-2 2xl:col-end-3 shadow shadow-neutral-600"
		>
			{#if logIn}
				<h3 class="my-6 text-3xl font-bold bg-neutral-900">Log in</h3>
			{/if}
			{#if !logIn}
				<h3 class="my-6 text-3xl font-bold bg-neutral-900">Sign Up</h3>
			{/if}

			<form class="my-10">
				{#if logIn}
					<div class="my-2">
						<div>
							<label for="username" class="text-xl">Email</label>
						</div>
						<div>
							<input
								type="text"
								name="username"
								id="username"
								class="logIn-btn"
								placeholder="example@email.com"
								size="40"
							/>
						</div>
					</div>

					<div class="my-2">
						<div>
							<label for="password" class="text-xl">Password</label>
						</div>
						<div>
							<input
								type="text"
								name="password"
								id="password"
								class="logIn-btn"
								placeholder="******"
								size="40"
							/>
						</div>
					</div>
				{/if}
				{#if !logIn}
					<div class="my-2">
						<div>
							<label for="username" class="text-xl">Email</label>
						</div>
						<div>
							<input
								type="text"
								name="username"
								id="username"
								class="logIn-btn"
								placeholder="example@email.com"
								size="40"
							/>
						</div>
					</div>

					<div class="my-2">
						<div>
							<label for="password" class="text-xl">Password</label>
						</div>
						<div>
							<input
								type="text"
								name="password"
								id="password"
								class="logIn-btn"
								placeholder="******"
								size="40"
							/>
						</div>
					</div>
					<div class="my-2">
						<div>
							<label for="password" class="text-xl">Verify Password</label>
						</div>
						<div>
							<input
								type="text"
								name="password"
								id="password"
								class="logIn-btn"
								placeholder="******"
								size="40"
							/>
						</div>
					</div>
				{/if}
				{#if logIn}
					<Button on:click={handleLogIn} let:logInName><p slot="logIn">{logInName}</p></Button>
				{/if}
				{#if !logIn}
					<Button on:click={handleLogIn} let:signUpName><p slot="signUp">{signUpName}</p></Button>
				{/if}
			</form>
		</section>
	{/if}
</section>

<style>
</style>
