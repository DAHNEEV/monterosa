<script lang="ts">
	import NavbarMobile from './navbar-mobile.svelte';
	import NavbarDesktop from './navbar-desktop.svelte';
	import { MediaQuery } from 'svelte/reactivity';

	const navbarLinks = [
		{
			title: 'Willa',
			href: '/willa',
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		},
		{
			title: 'Restauracja',
			href: '/restauracja',
			img: 'https://monterosa.pl/images/srednie/2024/06/resauracja-noc-1920.jpg'
		},
		{
			title: 'Bilard',
			href: '/bilard',
			img: 'https://monterosa.pl/images/srednie/2024/05/billard_1.jpg'
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
