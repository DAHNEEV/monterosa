<script>
	import { Accordion } from 'bits-ui';

	const menu = [
		{
			name: 'Zakąski',
			items: [
				{ name: 'Moskol z masłem czosnkowym', amount: '2 sztuki', price: 21 },
				{ name: 'Moskol z sosem borowikowym', amount: '2 sztuki', price: 25 },
				{ name: 'Łoscypek z grilla z żurawiną', price: 25 },
				{ name: 'Łoscypek z grilla z boczkiem', price: 25 }
			]
		},
		{
			name: 'Zupy',
			items: [
				{ name: 'Moskol z masłem czosnkowym', amount: '2 sztuki', price: 21 },
				{ name: 'Moskol z sosem borowikowym', amount: '2 sztuki', price: 25 },
				{ name: 'Łoscypek z grilla z żurawiną', price: 25 },
				{ name: 'Łoscypek z grilla z boczkiem', price: 25 }
			]
		},
		{
			name: 'Dania mięsne',
			items: [
				{ name: 'Moskol z masłem czosnkowym', amount: '2 sztuki', price: 21 },
				{ name: 'Moskol z sosem borowikowym', amount: '2 sztuki', price: 25 },
				{ name: 'Łoscypek z grilla z żurawiną', price: 25 },
				{ name: 'Łoscypek z grilla z boczkiem', price: 25 }
			]
		}
	];
</script>

<main class="mt-20 w-full p-4">
	<div class="mx-auto flex max-w-xl flex-col gap-8 rounded-2xl bg-background p-4">
		<div class="covered-by-your-grace-regular text-center text-6xl">Menu</div>
		<Accordion.Root type="multiple" class="flex flex-col gap-4">
			{#each menu as category, key}
				<Accordion.Item value="item-{key}">
					<div>
						<Accordion.Header>
							<Accordion.Trigger
								><div class="text-3xl">
									{category.name}
								</div></Accordion.Trigger
							>
						</Accordion.Header>
						<Accordion.Content>
							{#each category.items as item}
								<div class="bord flex w-full flex-row justify-between border-b p-2">
									<div>
										{item.name}
									</div>
									<div>
										{item.price} zł
									</div>
								</div>
							{/each}
						</Accordion.Content>
					</div>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
</main>
