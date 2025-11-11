<script>
	import { fly } from 'svelte/transition';
	import Inview from '../inview.svelte';
</script>

<Inview>
	<header
		in:fly={{ y: 60, duration: 700 }}
		class="mx-auto flex flex-col items-center justify-center"
	>
		<h1
			class="mb-4 text-4xl leading-none font-extrabold tracking-tight text-gray-900 md:text-5xl lg:text-6xl"
		>
			Twój dom w sercu gór
		</h1>
		<p class="mb-6 text-xl font-normal text-gray-800 sm:px-16 lg:text-2xl xl:px-48">
			Blisko Krupówek. Blisko Tatr. Blisko Ciebie.
		</p>
		<a
			href="#"
			class="inline-flex w-fit items-center justify-center rounded-lg bg-blue-700 px-5 py-3 text-center text-base font-medium text-white hover:bg-blue-800 focus:ring-4 focus:ring-blue-300"
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
	</header>
</Inview>
