<script lang="ts">
	import { Banknote } from 'lucide-svelte';
	import runeScroller from 'rune-scroller';
	import Bilard from '$lib/assets/billard.jpg?enhanced';
	import { resolve } from '$app/paths';
</script>

<div class="bg-bilard">
	<section class="relative flex w-full items-center justify-center overflow-hidden py-10">
		<enhanced:img class="absolute inset-0 h-full w-full object-cover" src={Bilard} alt="bilard" />
		<div class="absolute inset-0 bg-black/70"></div>
		<div
			use:runeScroller={{ animation: 'fade', duration: 1000 }}
			class="relative z-10 flex flex-col items-center gap-4 p-4 text-center text-neutral-200"
		>
			<h2 class="text-5xl font-extrabold tracking-tight md:text-6xl">Bilard</h2>
			<div class="flex flex-col gap-2 text-xl text-neutral-300">
				<div>Sala bilardowa z 7 stołami</div>
				<div class="flex items-center justify-center gap-2">
					<Banknote /> Cena 40 zł / 1 h (2 h tylko 60 zł)
				</div>
			</div>
			<a
				href={resolve('/bilard')}
				class="inline-flex w-fit items-center justify-center rounded-lg bg-bilard px-5 py-3 text-xl font-medium text-neutral-200 brightness-90 hover:brightness-75"
			>
				Więcej
				<svg
					class="ms-2 h-3.5 w-3.5 rtl:rotate-180"
					aria-hidden="true"
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 14 10"
				>
					<path
						stroke="currentColor"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M1 5h12m0 0L9 1m4 4L9 9"
					/>
				</svg>
			</a>
		</div>
	</section>
</div>
