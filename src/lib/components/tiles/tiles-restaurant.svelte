<script lang="ts">
	import { Clock } from 'lucide-svelte';
	import runeScroller from 'rune-scroller';
	import Food from '$lib/assets/food.jpg?enhanced';
</script>

<div class="bg-background">
	<section class="mx-auto flex w-full max-w-5xl flex-col gap-4 p-4 py-10 md:flex-row">
		<div
			use:runeScroller={{ animation: 'fade-in-left', duration: 1000 }}
			class="flex flex-col items-center gap-4 p-4 md:w-1/2 md:items-start md:justify-center"
		>
			<div class="flex items-center gap-2">
				<Clock />11:00–21:30
			</div>
			<h2 class="text-6xl leading-none font-extrabold tracking-tight text-primary md:text-7xl">
				Restauracja
			</h2>
			<div class="flex flex-col items-center gap-2 text-xl md:items-start">
				<div class="text-center md:text-left">
					<span class="inline-block break-inside-avoid"
						>Oferuje dania regionalne oraz kuchnię europejską.</span
					>
					<span class="inline-block break-inside-avoid">Duży wybór potraw.</span>
					<span class="inline-block break-inside-avoid">23 rodzaje pizzy.</span>
				</div>
			</div>
			<a
				href="/restauracja"
				class="inline-flex w-fit items-center justify-center rounded-lg bg-primary px-6 py-4 text-center text-3xl font-medium text-white hover:brightness-90"
			>
				Menu
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
		<div
			use:runeScroller={{ animation: 'fade-in-right', duration: 1000 }}
			class="overflow-hidden rounded-xl md:w-1/2"
		>
			<enhanced:img class="aspect-square h-full w-full object-cover" src={Food} alt="" />
		</div>
	</section>
</div>
