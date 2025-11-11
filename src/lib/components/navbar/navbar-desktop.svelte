<script lang="ts">
	/* eslint-disable */

	let { open = $bindable(), navbarLinks } = $props();
</script>

<div class="fixed top-1 z-50 flex w-full justify-center">
	<nav
		class="mx-1 flex h-fit items-center justify-around gap-4 rounded-2xl bg-neutral-900 px-4 text-lg font-semibold text-white"
	>
		<img src="https://monterosa.pl/graphic/logo.png" class="h-16 p-2" alt="" />
		{#each navbarLinks as item (item.title)}
			<a href={item.href} class="p-3 hover:underline">{item.title}</a>
		{/each}
		<a href="tel:+48123456789" class="p-3">+48 123 456 789</a>
	</nav>
</div>
