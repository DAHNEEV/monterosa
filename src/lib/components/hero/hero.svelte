<script>
	import HeroTitle from './hero-title.svelte';
	import Hale from '$lib/assets/hale.jpg?enhanced';
</script>

<main class="relative flex h-screen items-center justify-center">
	<div class="absolute inset-0 z-20 bg-black/30"></div>
	<HeroTitle />
	<enhanced:img
		class="absolute top-0 left-0 h-full w-full overflow-hidden object-cover"
		src={Hale}
		alt="hale"
	/>
</main>
