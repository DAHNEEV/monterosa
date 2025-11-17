<script lang="ts">
	const rooms = [
		{
			name: 'Pokój 1',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		},
		{
			name: 'Pokój 2',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		},
		{
			name: 'Pokój 3',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		},
		{
			name: 'Pokój 4',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		},
		{
			name: 'Pokój 5',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		},
		{
			name: 'Pokój 6',
			description: 'Komfortowy pokój z widokiem na morze',
			img: 'https://placehold.co/600x400/EEE/31343C'
		}
	];
</script>

<svelte:head>
	<title>Monte Rosa - Pokoje</title>
</svelte:head>

<main class="container mx-auto max-w-4xl px-4 pt-20 pb-8">
	<div class="grid grid-cols-1 gap-6 md:grid-cols-3">
		{#each rooms as room}
			<div class="mb-4 rounded-lg bg-white shadow-md">
				<img src={room.img} alt="Pokój 1" class="h-48 w-full rounded-lg object-cover" />
				<div class="p-4">
					<h3 class="text-lg font-semibold text-gray-800">{room.name}</h3>
					<p class="mt-1 text-sm text-gray-600">{room.description}e</p>
				</div>
			</div>
		{/each}
	</div>
</main>
