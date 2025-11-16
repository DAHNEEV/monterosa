<script lang="ts">
	import emblaCarouselSvelte from 'embla-carousel-svelte';
	import { type EmblaPluginType } from 'embla-carousel';
	import Autoplay from 'embla-carousel-autoplay';
	import runeScroller from 'rune-scroller';

	const emblaOptions = { loop: true };
	const emblaPlugins: EmblaPluginType[] = [Autoplay()];

	let slides = [
		{
			img: 'https://monterosa.pl/images/srednie/2025/04/3a-1920.jpg'
		},
		{
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		},
		{
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		}
	];
</script>

<div
	class="w-screen overflow-hidden bg-background py-4"
	use:emblaCarouselSvelte={{ options: emblaOptions, plugins: emblaPlugins }}
>
	<div use:runeScroller={{ animation: 'fade', duration: 3000 }} class="flex w-full">
		{#each slides as slide, index (index)}
			<div
				class="mr-4 w-full flex-[0_0_80%] overflow-hidden rounded-xl bg-amber-400 md:flex-[0_0_33.33%]"
			>
				<img src={slide.img} alt="" class="h-full w-full object-cover" />
			</div>
		{/each}
	</div>
</div>
