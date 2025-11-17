<script lang="ts">
	import emblaCarouselSvelte from 'embla-carousel-svelte';
	import { type EmblaPluginType } from 'embla-carousel';
	import Autoplay from 'embla-carousel-autoplay';
	import runeScroller from 'rune-scroller';
	import Willa1 from '$lib/assets/willa1.jpg?enhanced';
	import Willa2 from '$lib/assets/willa2.jpg?enhanced';
	import Willa3 from '$lib/assets/willa3.jpg?enhanced';
	import Willa4 from '$lib/assets/willa4.jpg?enhanced';

	const emblaOptions = { loop: true };
	const emblaPlugins: EmblaPluginType[] = [Autoplay()];

	let slides = [
		{
			title: 'Willa',
			href: '/willa',
			img: Willa1
		},
		{
			title: 'Willa',
			href: '/willa',
			img: Willa2
		},
		{
			title: 'Willa',
			href: '/willa',
			img: Willa3
		},
		{
			title: 'Willa',
			href: '/willa',
			img: Willa4
		}
	];
</script>

<div class="bg-primary">
	<section class="flex-colp-10 mx-auto flex w-full max-w-5xl md:flex-row">
		<div
			class="flex w-full flex-col items-center justify-center gap-8 px-6 py-10 text-background md:gap-4"
		>
			<h2
				use:runeScroller={{ animation: 'fade', duration: 1000 }}
				class="mb-2 text-6xl leading-none font-extrabold tracking-tight text-neutral-200"
			>
				Willa
			</h2>
			<p
				use:runeScroller={{ animation: 'fade', duration: 1000 }}
				class="mb-4 max-w-2xl text-center text-xl text-balance"
			>
				Klimatyczna willa z tradycją i nowoczesnym komfortem. To wyjątkowe miejsce położone w samym
				centrum Zakopanego – zaledwie 100 metrów od Krupówek, słynnego górskiego deptaku.
			</p>
			<div
				use:runeScroller={{ animation: 'fade', duration: 3000 }}
				class="w-screen overflow-hidden"
				use:emblaCarouselSvelte={{ options: emblaOptions, plugins: emblaPlugins }}
			>
				<div class="flex w-full">
					{#each slides as slide, index (index)}
						<div class="mr-4 w-full flex-[0_0_80%] overflow-hidden rounded-xl md:flex-[0_0_33.33%]">
							<enhanced:img src={slide.img} alt={slide.title} class="h-full w-full object-cover" />
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>
</div>
