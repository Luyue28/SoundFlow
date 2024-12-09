<script>
	import { onMount } from 'svelte';
	import '../app.css';

	let isMenuOpen = false;

	const toggleMenu = () => {
		isMenuOpen = !isMenuOpen;
	};

	const closeMenu = () => {
		isMenuOpen = false;
	};
</script>

<!-- Navigation Bar -->
<nav class="flex w-full items-center justify-between bg-white p-4 shadow-md">
	<!-- Logo -->
	<div class="logo flex items-center space-x-2">
		<a href="/" class="text-2xl font-bold italic text-blue-600">SoundFlow</a>
	</div>

	<!-- Desktop Navigation Links -->
	<div class="hidden space-x-6 md:flex">
		<a href="/note" class="text-lg text-gray-500 hover:text-gray-300">Note</a>
		<a href="/tutorial" class="text-lg text-gray-800 hover:text-gray-500">Tutorial</a>
		<a href="/workspace" class="text-lg text-gray-800 hover:text-gray-500">Workspace</a>
		<a href="/profile" class="text-lg text-gray-800 hover:text-gray-500">Profile</a>
		<a href="/about" class="text-lg text-gray-800 hover:text-gray-500">About</a>
	</div>

	<!-- Mobile Menu Button -->
	<div class="md:hidden">
		<!-- svelte-ignore a11y_consider_explicit_label -->
		<button class="text-gray-800 focus:outline-none" on:click={toggleMenu}>
			<svg
				class="h-6 w-6"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				></path>
			</svg>
		</button>
	</div>
</nav>

<!-- Mobile Navigation Menu -->
{#if isMenuOpen}
	<div class="absolute left-0 top-16 z-50 w-full bg-white p-4 shadow-md md:hidden">
		<a
			href="/note"
			class="mb-2 block text-lg text-gray-800 hover:text-gray-500 transition"
			on:click={closeMenu}
		>Note</a>
		<a
			href="/tutorial"
			class="mb-2 block text-lg text-gray-800 hover:text-gray-500 transition"
			on:click={closeMenu}
		>Tutorial</a>
		<a
			href="/workspace"
			class="mb-2 block text-lg text-gray-800 hover:text-gray-500 transition"
			on:click={closeMenu}
		>Workspace</a>
		<a
			href="/profile"
			class="mb-2 block text-lg text-gray-800 hover:text-gray-500 transition"
			on:click={closeMenu}
		>Profile</a>
		<a
			href="/about"
			class="mb-2 block text-lg text-gray-800 hover:text-gray-500 transition"
			on:click={closeMenu}
		>About</a>
	</div>
{/if}

<div class="layout relative flex min-h-screen flex-col">
	<main class="flex-1 p-4">
		<slot />
	</main>
</div>

<!-- Footer -->
<footer class="w-full bg-gray-100 py-8 text-center shadow-inner">
	<div class="footer-logo md:text-center">
		<h1 class="text-2xl font-bold italic text-blue-600">SoundFlow</h1>
		<p class="mt-2 text-gray-700">
			Keep focused and productive with customizable white noise templates, task management, and
			analytics...<br />All tailored to help you stay in the zone!
		</p>
	</div>
	<div class="mt-6 border-t border-gray-300 pt-4">
		<p class="text-gray-500">© 2024 SoundFlow by Luyue Zhang. All rights reserved.</p>
	</div>
</footer>

<style>
	nav {
		position: relative;
	}

	footer {
		background: #f9fafb;
		box-shadow: 0 -4px 8px rgba(0, 0, 0, 0.05);
		font-family: 'Arial', sans-serif;
	}

	.layout {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}

	main {
		flex-grow: 1;
	}
</style>
