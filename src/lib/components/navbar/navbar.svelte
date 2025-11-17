<script lang="ts">
	import NavbarMobile from './navbar-mobile.svelte';
	import NavbarDesktop from './navbar-desktop.svelte';
	import { MediaQuery } from 'svelte/reactivity';
	import Pokoje from '$lib/assets/pokoje.jpg?enhanced';
	import Restauracja from '$lib/assets/restauracja.jpg?enhanced';
	import Bilard from '$lib/assets/billard.jpg?enhanced';

	const navbarLinks = [
		{
			title: 'Willa',
			href: '/willa',
			img: Pokoje
		},
		{
			title: 'Restauracja',
			href: '/restauracja',
			img: Restauracja
		},
		{
			title: 'Bilard',
			href: '/bilard',
			img: Bilard
		}
	];

	let open = $state(false);
	const isDesktop = new MediaQuery('(min-width: 448px)');

	$effect(() => {
		if (isDesktop.current) {
			open = false;
		}
	});
</script>

<div class="desktop-only">
	<NavbarDesktop {navbarLinks} />
</div>
<div class="mobile-only">
	<NavbarMobile {navbarLinks} bind:open />
</div>

<style>
	.desktop-only {
		display: none;
	}
	.mobile-only {
		display: block;
	}
	@media (min-width: 635px) {
		.desktop-only {
			display: block;
		}
		.mobile-only {
			display: none;
		}
	}
</style>
