<script lang="ts">
	/* eslint-disable */
	import Logo from '$lib/assets/logo.png?enhanced';
	import { resolve } from '$app/paths';

	let { open = $bindable(), navbarLinks } = $props();
</script>

<div class="fixed top-1 z-50 flex w-full justify-center">
	<nav
		class="mx-1 flex h-fit items-center justify-around gap-4 rounded-2xl bg-neutral-900 px-4 text-lg font-semibold text-white"
	>
		<a href={resolve('/')}>
			<enhanced:img src={Logo} class="h-16 w-auto object-contain p-2" alt="logo" />
		</a>
		{#each navbarLinks as item (item.title)}
			<a href={resolve(item.href)} class="p-3 hover:underline">{item.title}</a>
		{/each}
		<a href="tel:+48123456789" class="p-3">+48 123 456 789</a>
	</nav>
</div>
