<script lang="ts">
	import emblaCarouselSvelte from 'embla-carousel-svelte';
	import { type EmblaPluginType } from 'embla-carousel';
	import { inview } from 'svelte-inview';
	import { fade } from 'svelte/transition';
	import Autoplay from 'embla-carousel-autoplay';

	let visible = false;
	const options = {
		threshold: 0.5
	};
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
	<section
		use:inview={options}
		on:inview_enter={() => {
			visible = true;
		}}
		class="mx-auto flex min-h-screen w-full max-w-5xl flex-col p-4 md:flex-row"
	>
		{#if visible}
			<div
				in:fade={{ duration: 1000 }}
				class="flex h-screen w-full flex-col items-center justify-center gap-8 p-4 text-background md:gap-4"
			>
				<h2 class="mb-2 text-6xl leading-none font-extrabold tracking-tight md:text-7xl">Willa</h2>
				<p class="mb-4 max-w-2xl text-center text-xl text-balance">
					Klimatyczna willa z tradycją i nowoczesnym komfortem. To wyjątkowe miejsce położone w
					samym centrum Zakopanego – zaledwie 100 metrów od Krupówek, słynnego górskiego deptaku.
				</p>
				<div
					class="w-screen overflow-hidden"
					use:emblaCarouselSvelte={{ options: emblaOptions, plugins: emblaPlugins }}
				>
					<div class="flex w-full">
						{#each slides as slide, index (index)}
							<div
								class="mr-4 w-full flex-[0_0_80%] overflow-hidden rounded-xl bg-amber-400 md:flex-[0_0_50%]"
							>
								<img src={slide.img} alt="" class="h-full w-full object-cover" loading="lazy" />
							</div>
						{/each}
					</div>
				</div>
			</div>
		{/if}
	</section>
</div>
