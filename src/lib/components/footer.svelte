<script lang="ts">
	import { Phone } from 'lucide-svelte';

	const navbarLinks = [
		{
			title: 'Willa',
			href: '/willa',
			img: 'https://monterosa.pl/images/onas/2024/05/noclegi_1.jpg'
		},
		{
			title: 'Restauracja',
			href: '/restauracja',
			img: 'https://monterosa.pl/images/srednie/2024/06/resauracja-noc-1920.jpg'
		},
		{
			title: 'Bilard',
			href: '/bilard',
			img: 'https://monterosa.pl/images/srednie/2024/05/billard_1.jpg'
		}
	];
</script>

<footer
	class="flex flex-col justify-around gap-10 bg-primary p-10 text-2xl text-background md:flex-row"
>
	<div class="flex flex-col items-center gap-4 md:items-start">
		{#each navbarLinks as item (item.title)}
			<a href={item.href} class="underline">
				{item.title}
			</a>
		{/each}
	</div>
	<div class="flex flex-col items-center gap-4 text-xl md:items-end md:text-2xl">
		<div class="flex items-center justify-center gap-2 md:justify-end"><Phone /> Kontakt</div>
		<a href="tel:1234567890">Restauracja: +48 123 123 123</a>
		<a href="tel:1234567890">Willa/Bilard: +48 123 123 123</a>
	</div>
</footer>
