<script>
	import runeScroller from 'rune-scroller';
	import { onMount } from 'svelte';

	let wiggling = $state(false);

	onMount(() => {
		const interval = setInterval(() => {
			wiggling = true;
			setTimeout(() => {
				wiggling = false;
			}, 1000); // animacja trwa 1 sekundę
		}, 5000); // co 5 sekund

		return () => clearInterval(interval);
	});
</script>

<div
	use:runeScroller={{ animation: 'fade-in-up', duration: 1000 }}
	class="z-30 mx-auto flex flex-col items-center justify-center p-4 text-center text-balance"
>
	<h1 class="mb-4 text-5xl leading-none font-extrabold tracking-tight text-neutral-100 md:text-6xl">
		Twój dom w sercu gór
	</h1>
	<p class="mb-6 text-xl font-normal text-neutral-200 sm:px-16 lg:text-2xl xl:px-48">
		<span class="whitespace-nowrap">Blisko Krupówek.</span>
		<span class="whitespace-nowrap">Blisko Tatr.</span>
		<span class="whitespace-nowrap">Blisko Ciebie.</span>
	</p>
	<a
		target="_blank"
		class:wiggle={wiggling}
		href="https://www.booking.com/hotel/pl/willa-monte-rosa.pl.html"
		class="inline-flex w-fit items-center justify-center rounded-lg bg-blue-700 px-5 py-3 text-center font-medium text-white hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 md:text-xl"
	>
		Zarezerwuj na Booking.com
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

<style>
	.wiggle {
		animation: wiggle 1s cubic-bezier(0.36, 0.07, 0.19, 0.97) 4;
	}

	@keyframes wiggle {
		0%,
		100% {
			transform: translateX(0) rotate(0deg);
		}
		10%,
		30%,
		50%,
		70%,
		90% {
			transform: translateX(-2px) rotate(-1deg);
		}
		20%,
		40%,
		60%,
		80% {
			transform: translateX(2px) rotate(1deg);
		}
	}
</style>
