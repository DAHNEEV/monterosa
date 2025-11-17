<script lang="ts">
	import emblaCarouselSvelte from 'embla-carousel-svelte';
	import { type EmblaPluginType } from 'embla-carousel';
	import Autoplay from 'embla-carousel-autoplay';
	import runeScroller from 'rune-scroller';
	import Food1 from '$lib/assets/food1.jpg?enhanced';
	import Food2 from '$lib/assets/food.jpg?enhanced';
	import Food3 from '$lib/assets/food3.jpg?enhanced';
	import Food4 from '$lib/assets/food4.jpg?enhanced';

	const emblaOptions = { loop: true };
	const emblaPlugins: EmblaPluginType[] = [Autoplay()];

	let slides = [
		{
			alt: 'food 1',
			img: Food1
		},
		{
			alt: 'food 2',
			img: Food2
		},
		{
			alt: 'food 3',
			img: Food3
		},
		{
			alt: 'food 4',
			img: Food4
		}
	];
</script>

<div class="w-screen bg-background">
	<div
		use:runeScroller={{ animation: 'fade-in-right', duration: 1000 }}
		class="w-screen overflow-hidden py-4"
		use:emblaCarouselSvelte={{ options: emblaOptions, plugins: emblaPlugins }}
	>
		<div class="flex w-full">
			{#each slides as slide, index (index)}
				<div class="mr-4 w-full flex-[0_0_80%] overflow-hidden rounded-xl md:flex-[0_0_33.33%]">
					<enhanced:img
						src={slide.img}
						alt={slide.alt}
						class="aspect-video h-full w-full object-cover"
					/>
				</div>
			{/each}
		</div>
	</div>
</div>
