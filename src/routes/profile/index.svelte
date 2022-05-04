<script>
	let loggedIn = false;
</script>

<section id="profilePage" class="grid grid-cols-3">
	<section class="headings col-span-3">
		<h2 class="my-2 bg-neutral-900">Profile</h2>
	</section>

	{#if !loggedIn}
		<section
			id="logIn"
			class="bg-neutral-700 my-10 rounded-lg text-center font-bold col-start-2 col-end-3"
		>
			<h3 class="mt-6 text-4xl">Log in</h3>

			<!-- <section> -->
			<form class="my-10">
				<div class="my-2">
					<div>
						<label for="username">Email</label>
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
						<label for="password">Password</label>
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
			</form>
			<!-- </section> -->
		</section>
	{/if}
</section>

<style>
	#logIn {
		/* width: 20rem;
		height: 20rem; */
	}
</style>
