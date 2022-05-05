<script>
	let navLinks = [
		{
			name: 'Home',
			href: '/',
			svg: `<svg
					class="inline"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="-2 -2 24 24"
					width="24"
					fill="currentColor">
					<path
						d="M18 18V7.132l-8-4.8-8 4.8V18h4v-2.75a4 4 0 1 1 8 0V18h4zm-6 2v-4.75a2 2 0 1 0-4 0V20H2a2 2 0 0 1-2-2V7.132a2 2 0 0 1 .971-1.715l8-4.8a2 2 0 0 1 2.058 0l8 4.8A2 2 0 0 1 20 7.132V18a2 2 0 0 1-2 2h-6z">
					</path>
					</svg
				 >`
		},
		{
			name: 'Calcs',
			href: '/calcs',
			svg: `<svg
					class="inline"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="-4.5 -2 24 24"
					width="24"
					fill="currentColor"
					><path
						d="M4 2a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h7a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2H4zm0-2h7a4 4 0 0 1 4 4v12a4 4 0 0 1-4 4H4a4 4 0 0 1-4-4V4a4 4 0 0 1 4-4z"
					/><path
						d="M5 4h5a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1zm0 5h1a1 1 0 0 1 1 1v1a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1v-1a1 1 0 0 1 1-1zm4 0h1a1 1 0 0 1 1 1v1a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-1a1 1 0 0 1 1-1zm0 4h1a1 1 0 0 1 1 1v1a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-1a1 1 0 0 1 1-1zm-4 0h1a1 1 0 0 1 1 1v1a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1v-1a1 1 0 0 1 1-1z"
					/></svg
				>`
		},
		{
			name: 'Blog',
			href: '/blogs',
			svg: `<svg
					class="inline"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="-2 -2 24 24"
					width="24"
					fill="currentColor"
					><path
						d="M11.81 15c1.744 0 3.16-1.42 3.17-3.154L15 9.293l-.03-.14-.083-.174-.142-.11c-.184-.144-1.116.01-1.367-.218-.178-.163-.206-.456-.26-.855-.1-.771-.163-.811-.284-1.073-.44-.929-1.63-1.627-2.448-1.723H8.169A3.174 3.174 0 0 0 5 8.16v3.686C5 13.58 6.426 15 8.17 15h3.64zm-3.6-7.419h1.757c.335 0 .607.273.607.604 0 .33-.272.604-.607.604H8.21a.608.608 0 0 1-.607-.604c0-.331.271-.604.607-.604zM7.603 11.8c0-.33.271-.601.607-.601h3.57c.333 0 .604.27.604.601 0 .327-.27.601-.604.601H8.21a.607.607 0 0 1-.607-.601z"
					/><path
						d="M4 2a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2H4zm0-2h12a4 4 0 0 1 4 4v12a4 4 0 0 1-4 4H4a4 4 0 0 1-4-4V4a4 4 0 0 1 4-4z"
					/></svg
				>`
		},
		{
			name: 'Guides',
			href: '/guides',
			svg: `<svg class="inline" xmlns="http://www.w3.org/2000/svg" viewBox="-5 -2 24 24" width="24" fill="currentColor"
					><path
						d="M5 18v2H3v-2H0V0h11a3 3 0 0 1 3 3v12a3 3 0 0 1-3 3H5zM3 2H2v14h1V2zm2 0v14h6a1 1 0 0 0 1-1V3a1 1 0 0 0-1-1H5zm1 2h5v2H6V4zm0 3h5v2H6V7z"
					/></svg
				>`
		},
		{
			name: 'Coaches',
			href: '/coaches',
			svg: `<svg class="inline" xmlns="http://www.w3.org/2000/svg" viewBox="-5 -2 24 24" width="24" fill="currentColor"
					><path
						d="M3.534 10.07a1 1 0 1 1 .733 1.86A3.579 3.579 0 0 0 2 15.26V17a1 1 0 0 0 1 1h8a1 1 0 0 0 1-1v-1.647a3.658 3.658 0 0 0-2.356-3.419 1 1 0 1 1 .712-1.868A5.658 5.658 0 0 1 14 15.353V17a3 3 0 0 1-3 3H3a3 3 0 0 1-3-3v-1.74a5.579 5.579 0 0 1 3.534-5.19zM7 0a4 4 0 0 1 4 4v2a4 4 0 1 1-8 0V4a4 4 0 0 1 4-4zm0 2a2 2 0 0 0-2 2v2a2 2 0 1 0 4 0V4a2 2 0 0 0-2-2z"
					/></svg
				>`
		},
		{
			name: 'About',
			href: '/about',
			svg: `<svg class="inline" xmlns="http://www.w3.org/2000/svg" viewBox="-2 -2 24 24" width="24" fill="currentColor"
					><path
						d="M10 20C4.477 20 0 15.523 0 10S4.477 0 10 0s10 4.477 10 10-4.477 10-10 10zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm0-10a1 1 0 0 1 1 1v5a1 1 0 0 1-2 0V9a1 1 0 0 1 1-1zm0-1a1 1 0 1 1 0-2 1 1 0 0 1 0 2z"
					/></svg
				>`
		}
	];

	let profileLinks = [
		{ name: 'Profile', href: '/profile' },
		{ name: 'Subscriptions', href: '/profile/subscriptions' },
		{ name: 'Settings', href: '/profile/pro-settings' }
	];

	let proSvg = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="-2 -2 24 24" height="70" width="70" fill="currentColor"
					><path
						d="M10 20C4.477 20 0 15.523 0 10S4.477 0 10 0s10 4.477 10 10-4.477 10-10 10zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm0-14a4 4 0 0 1 4 4v2a4 4 0 1 1-8 0V8a4 4 0 0 1 4-4zm0 2a2 2 0 0 0-2 2v2a2 2 0 1 0 4 0V8a2 2 0 0 0-2-2zM5.91 16.876a8.033 8.033 0 0 1-1.58-1.232 5.57 5.57 0 0 1 2.204-1.574 1 1 0 1 1 .733 1.86c-.532.21-.993.538-1.358.946zm8.144.022a3.652 3.652 0 0 0-1.41-.964 1 1 0 1 1 .712-1.868 5.65 5.65 0 0 1 2.284 1.607 8.032 8.032 0 0 1-1.586 1.225z"
					/>
				</svg>`;

	let blog = {
		name: 'Read Article',
		href: './blogs'
	};

	let calcBtn = {
		name: 'Calculate Your Freedom',
		href: './calcs'
	};

	let calculate = {
		name: 'Calculate'
	};

	let serviceBtn = {
		name: 'Read More',
		href: './coaches'
	};

	let errorPage = {
		name: 'Visit Home Page',
		href: '/'
	};

	let signUpBtn = {
		name: 'Sign Up'
	};

	let logInBtn = {
		name: 'Log In'
	};
</script>

{#if $$slots.navLinks}
	{#each navLinks as { name, href, svg }}
		<a class="grid" {href}>
			<button on:click class="nav-btn">
				<slot name="navLinks" navName={name} />
				{@html svg}
			</button>
		</a>
	{/each}
{/if}

{#if $$slots.profile}
	<button on:click class="profile-btn">
		<slot name="profile" {proSvg} />
	</button>
{/if}

{#if $$slots.profileLinks}
	{#each profileLinks as { name, href }}
		<a class="grid" {href}>
			<button on:click class="nav-btn">
				<slot name="profileLinks" proName={name} />
			</button>
		</a>
	{/each}
{/if}

{#if $$slots.blog}
	<a href={blog.href} class="grid">
		<button on:click class="nav-btn">
			<slot name="blog" blogName={blog.name} />
		</button>
	</a>
{/if}

{#if $$slots.calcs}
	<a href={calcBtn.href} class="grid col-start-2 col-end-4">
		<button on:click class="nav-btn">
			<slot name="calcs" calcName={calcBtn.name} />
		</button>
	</a>
{/if}

{#if $$slots.calculate}
	<button on:click class="justify-self-end nav-btn">
		<slot name="calculate" calculate={calculate.name} />
	</button>
{/if}

{#if $$slots.services}
	<a href={serviceBtn.href} class="grid">
		<button on:click class="nav-btn">
			<slot name="services" serviceName={serviceBtn.name} />
		</button>
	</a>
{/if}

{#if $$slots.error}
	<a href={errorPage.href} class="grid">
		<button on:click class="nav-btn">
			<slot name="error" errorName={errorPage.name} />
		</button>
	</a>
{/if}

{#if $$slots.signUp}
	<button on:click class="signUp-btn">
		<slot name="signUp" signUpName={signUpBtn.name} />
	</button>
{/if}

{#if $$slots.logIn}
	<button on:click class="signUp-btn">
		<slot name="logIn" logInName={logInBtn.name} />
	</button>
{/if}
