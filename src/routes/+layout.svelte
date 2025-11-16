<script lang="ts">
	import '../app.css';
	import 'rune-scroller/animations.css';
	import favicon from '$lib/assets/favicon.svg';
	import Navbar from '$lib/components/navbar/navbar.svelte';
	import Footer from '$lib/components/footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div data-vaul-drawer-wrapper class="flex min-h-screen flex-col">
	<Navbar />
	<div class="flex-1">
		{@render children()}
	</div>
	<Footer />
</div>
