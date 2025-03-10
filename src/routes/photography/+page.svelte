<script>
	let cards = [
		{
			title: 'South Africa',
			year: '2020',
			url: '/photography/south-africa',
			img: '/photo/south-africa/b2df4903-a131-4de4-aa1b-b26c70ab87c8_rw_600.jpg'
		},
		{
			title: 'Iceland',
			year: '2019',
			url: '/photography/iceland',
			img: '/photo/iceland/b700ed70-d3aa-4180-a1cf-f92e2a57ce74_rw_600.jpg'
		},
		{
			title: 'Auvergne',
			year: '2018',
			url: '/photography/auvergne',
			img: '/photo/auvergne/24e2fd6d-62f4-443d-9f49-cf8fd1952b59_rw_1920.jpg'
		},
		{
			title: 'Greece',
			year: '2017',
			url: '/photography/greece',
			img: '/photo/greece/d24627cf-21dc-4d27-a795-e542104cbf48_rw_600.jpg'
		},
		{
			title: 'Scandinavia',
			year: '2016',
			url: '/photography/scandinavia',
			img: '/photo/scandinavia/222766da-6376-40af-a8c3-19cde6b5a4b4_rw_600.jpg'
		},
		{
			title: 'Thailand',
			year: '2016',
			url: '/photography/thailand',
			img: '/photo/thailand/9ec68037-e719-44d8-a432-ac3e24f41a60_rw_600.jpg'
		},
		{
			title: 'Paris',
			year: '2016',
			url: '/photography/paris',
			img: '/photo/paris/fd1af66a-1658-46fc-a6cd-8c2fc156dfb5_rw_1920.jpg'
		},
		{
			title: 'Bordeaux',
			year: '2016',
			url: '/photography/bordeaux',
			img: '/photo/bordeaux/c5eee68e-bf11-4bb0-b815-3be2db159c7d.jpg'
		},
		{
			title: "Sables d'Olonne",
			year: '2016',
			url: '/photography/sables-dolonne',
			img: '/photo/sables-dolonne/f5dad358-495b-44b9-a455-36075f662cad.jpg'
		},
		{
			title: 'Brittany',
			year: '1990',
			url: '/photography/brittany',
			img: '/photo/brittany/066cf4ce-b8a0-4dd0-9380-81c8525e4aad.jpg'
		}
	];
	// Doing right/left layout with css produces errors out of the box
</script>

<svelte:head>
	<title>Photography | Anthony Graignic</title>
	<meta name="description" content="Anthony Graignic's Photography Portfolio" />
</svelte:head>

<main class="grid grid-cols-1 gap-4 p-4 font-mono lg:w-5xl">
	{#each cards as card, i}
		<a
			href={card.url}
			class="grid grid-cols-5 items-center rounded-lg border border-gray-200 bg-white shadow-sm hover:bg-gray-100 dark:border-gray-700 dark:bg-gray-800 dark:hover:bg-gray-700"
		>
			{#if i % 2 == 0}
				<img
					class="col-span-3 rounded-t-lg object-cover md:rounded-none md:rounded-s-lg"
					src={card.img}
					alt=""
				/>
				<div class="col-span-2 flex flex-col items-center justify-between p-4 leading-normal">
					<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
						{card.title}
					</h5>
					<p class="text-gray-700 dark:text-gray-300">{card.year}</p>
				</div>
			{:else}
				<div class="col-span-2 flex flex-col items-center justify-between p-4 leading-normal">
					<h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white">
						{card.title}
					</h5>
					<p class="text-gray-700 dark:text-gray-300">{card.year}</p>
				</div>
				<img
					class="col-span-3 rounded-t-lg object-cover md:rounded-none md:rounded-e-lg"
					src={card.img}
					alt=""
				/>
			{/if}
		</a>
	{/each}
</main>
