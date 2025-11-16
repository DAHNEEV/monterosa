<script lang="ts">
	import emblaCarouselSvelte from 'embla-carousel-svelte';
	import { type EmblaPluginType } from 'embla-carousel';
	import Autoplay from 'embla-carousel-autoplay';
	import runeScroller from 'rune-scroller';

	const emblaOptions = { loop: true };
	const emblaPlugins: EmblaPluginType[] = [Autoplay()];

	let slides = [
		{
			title: 'Willa',
			href: '/willa',
			img: 'https://monterosa.pl/images/srednie/2025/04/3a-1920.jpg'
		},
		{
			title: 'Willa',
			href: '/willa',
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		},
		{
			title: 'Willa',
			href: '/willa',
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		}
	];
</script>

<div class="bg-primary">
	<section class="mx-auto flex w-full max-w-5xl flex-col p-10 md:flex-row">
		<div
			class="flex w-full flex-col items-center justify-center gap-8 p-4 text-background md:gap-4"
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
						<div
							class="mr-4 w-full flex-[0_0_80%] overflow-hidden rounded-xl bg-amber-400 md:flex-[0_0_33.33%]"
						>
							<img src={slide.img} alt="" class="h-full w-full object-cover" />
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>
</div>
