<script>
	import { inview } from 'svelte-inview';
	import { fly } from 'svelte/transition';

	let visible = false;
	const options = {
		threshold: 1
	};
</script>

<div
	use:inview={options}
	on:inview_enter={() => {
		visible = true;
	}}
	class="flex min-h-[30vh] items-center justify-center"
>
	{#if visible}
		<article
			in:fly={{ y: 60, duration: 700 }}
			class="mx-auto flex flex-col items-center justify-center p-8 md:w-1/2"
		>
			<h2
				class="mb-4 text-center text-4xl leading-none font-extrabold tracking-tight text-gray-900 md:text-5xl"
			>
				W sercu Zakopanego
			</h2>
		</article>
	{/if}
</div>
