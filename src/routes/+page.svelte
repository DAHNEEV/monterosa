<script>
	import Description from '$lib/components/description.svelte';
	import Hero from '$lib/components/hero/hero.svelte';
	import Navbar from '$lib/components/navbar/navbar.svelte';
	import Tiles from '$lib/components/tiles/tiles.svelte';
</script>

<div data-vaul-drawer-wrapper>
	<Navbar></Navbar>
	<Hero />
	<Description />
	<Tiles />
</div>
