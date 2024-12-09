<script>
	import '../app.css';
</script>

<nav class="flex w-full items-center justify-between bg-white p-4 shadow-md">
	<div class="logo flex items-center space-x-2">
		<a href="/" class="text-2xl font-bold italic text-blue-600">SoundFlow</a>
	</div>
	<div class="nav-links hidden space-x-6 md:flex">
		<a href="/" class="text-xl text-gray-800 hover:text-gray-500">Home</a>
		<a href="/contact" class="text-xl text-gray-800 hover:text-gray-500">Contact</a>
	</div>
</nav>

<div class="layout relative flex min-h-screen flex-col">
	<main class="flex-1 p-4">
		<slot />
	</main>	
</div>

<!-- Footer -->
<footer class="w-full bg-gray-100 py-8 text-center shadow-inner">
	<div class="footer-logo md:text-center">
		<h1 class="text-2xl font-bold italic text-blue-600">SoundFlow</h1>
		<p class="mt-2 text-gray-700">A tool for helping you manage the playlists.</p>
	</div>
	<div class="mt-6 border-t border-gray-300 pt-4">
		<p class="text-gray-600">© 2024 SoundFlow. All rights reserved.</p>
	</div>
</footer>

<style>
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
