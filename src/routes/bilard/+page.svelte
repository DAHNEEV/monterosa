<script>
	import { Banknote } from 'lucide-svelte';
	import runeScroller from 'rune-scroller';
	import Bilard from '$lib/assets/billard.jpg?enhanced';
</script>

<svelte:head>
	<title>Monte Rosa - Bilard</title>
</svelte:head>

<main class="relative flex h-screen w-full items-center justify-center">
	<enhanced:img
		class="absolute inset-0 top-0 left-0 h-full w-full object-cover"
		src={Bilard}
		alt="bilard"
	/>
	<div class="absolute inset-0 bg-black/50"></div>
	<div
		use:runeScroller={{ animation: 'fade-in-up', duration: 1000 }}
		class="z-20 flex max-w-md flex-col items-center justify-center gap-4 text-neutral-100"
	>
		<h1 class="text-7xl font-bold">Bilard</h1>
		<div class="flex flex-col items-center justify-center gap-4 text-xl text-neutral-200">
			<div>Sala bilardowa z 7 stołami</div>
			<div class="flex items-center justify-center gap-2">
				<Banknote /> Cena 40 zł / 1 h (2 h tylko 60 zł)
			</div>
		</div>
	</div>
</main>
