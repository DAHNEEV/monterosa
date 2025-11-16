<script lang="ts">
	/* eslint-disable */
	import { AspectRatio } from 'bits-ui';
	import { Menu } from 'lucide-svelte';
	import { Drawer } from 'vaul-svelte';

	let { open = $bindable(), navbarLinks } = $props();
</script>

<Drawer.Root bind:open>
	<nav class="fixed top-0 z-40 flex h-16 w-screen items-center justify-between bg-neutral-900 px-4">
		<a href="/"><img src="https://monterosa.pl/graphic/logo.png" class="h-12" alt="" /></a>
		<Drawer.Trigger class="text-neutral-100"><Menu /></Drawer.Trigger>
	</nav>
	<Drawer.Portal>
		<Drawer.Overlay />
		<Drawer.Content
			class="fixed right-0 bottom-0 left-0 z-50 mt-24 flex h-fit max-h-[90%] flex-col rounded-t-[10px]"
		>
			<div class="flex-1 overflow-auto rounded-t-[10px] bg-zinc-200 p-4 pb-6">
				<div class="mx-auto mb-6 h-1.5 w-12 flex-shrink-0 rounded-full bg-zinc-300" />
				<div class="mx-auto flex max-w-md flex-col gap-6">
					{#each navbarLinks as item (item.title)}
						<AspectRatio.Root ratio={2 / 1} class="overflow-hidden rounded-2xl">
							<a
								href={item.href}
								class="flex h-full w-full items-center justify-center overflow-hidden"
							>
								<img class="h-full w-full object-cover" src={item.img} alt="" />
								<div class="absolute inset-0 bg-black/50"></div>
								<h1 class="absolute text-5xl font-semibold tracking-wide text-white">
									{item.title}
								</h1>
							</a>
						</AspectRatio.Root>
					{/each}
				</div>
			</div>
		</Drawer.Content>
	</Drawer.Portal>
</Drawer.Root>
