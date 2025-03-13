<script>
	import CvElement from '$lib/components/CvElement.svelte';

	let work = [
		{
			company: 'Clermont Auvergne Innovation',
			logo: '/logos/satt_grand_centre_logo.jpeg',
			position: 'Research Engineer',
			website: 'https://www.clermontauvergneinnovation.com/',
			startDate: '2024-05-21'
			// endDate: '2025-11-21',
		},
		{
			company: 'UCA',
			logo: '/logos/universite_clermont_auvergne_logo.jpeg',
			position: 'Scientific Computation Engineer',
			website: 'https://ecomobicoin.limos.fr',
			startDate: '2022-10-03',
			endDate: '2024-03-31'
		},
		{
			company: 'Freelancer',
			logo: '/favicon-96x96.png',
			position: 'Identity & Access Management (IAM) Solution Architect',
			website: 'https://anthonygraignic.tech',
			startDate: '2022-01-23',
			endDate: '2022-10-03'
		},
		{
			company: 'Stendhal',
			logo: '/logos/stendhal.png',
			position: 'Co-founder,  CTO',
			website: 'https://stendhal.ai',
			startDate: '2020-05-01',
			endDate: '2022-01-23'
		},
		{
			company: 'Yesitis',
			logo: '/logos/yesitis.jpg',
			position: 'CTO / Solution Architect',
			website: 'http://yesitis.fr',
			startDate: '2017-01-23',
			endDate: '2020-02-01'
		},
		{
			company: "Sopra Steria -  SNCF & Ritm'x",
			logo: '/logos/ritmx_logo.jpeg',
			position: 'Android Architect, ticketing expert',
			website: 'https://www.soprasteria.com/',
			startDate: '2016-01-01',
			endDate: '2017-01-17'
		},
		{
			company: 'Sopra Steria - SNCF ticketing service center',
			logo: '/logos/sncf-logo.jpg',
			position: 'NFC ticketing solutions manager & Android Architect',
			website: 'https://www.soprasteria.com/',
			startDate: '2015-01-01',
			endDate: '2016-01-01'
		},
		{
			company: 'Sopra Steria',
			logo: '/logos/soprasteria_logo.jpeg',
			position: 'Software developer',
			website: 'https://www.soprasteria.com/',
			startDate: '2013-09-01',
			endDate: '2014-12-31'
		}
	];
	let education = [
		{
			institution: 'École Polytechnique Fédérale de Lausanne ',
			logo: '/logos/epfl-logo.png',
			area: 'Electrical Engineering',
			studyType: 'Exchange semester',
			startDate: '2012-09-01',
			endDate: '2013-02-01'
		},
		{
			institution: 'Grenoble INP – Esisar ',
			logo: '/logos/logo_Grenoble_INP_-_Esisar.svg',
			area: 'Embedded Software Development',
			studyType: 'Engineering Degree',
			startDate: '2010-01-01',
			endDate: '2013-07-01'
		}
	];
</script>

<svelte:head>
	<title>Curriculum Vitae | Anthony Graignic</title>
	<meta name="description" content="Professional experiences and education" />
</svelte:head>
<main
	class="mx-auto grid max-w-4xl auto-cols-max grid-cols-1 items-center justify-center justify-items-center p-4 font-mono"
>
	<h1>Work</h1>
	<ol class="mt-6 w-full">
		{#each work as { company, logo, position, startDate, endDate }, i}
			<CvElement
				title={company}
				{logo}
				subtitle={position}
				isLastElement={i !== work.length - 1}
				{startDate}
				{endDate}
			/>
		{/each}
	</ol>
	<h1>Education</h1>
	<ol class="mt-6 w-full">
		{#each education as { institution, logo, studyType, startDate, endDate }, i}
			<CvElement
				title={institution}
				{logo}
				subtitle={studyType}
				isLastElement={i !== education.length - 1}
				{startDate}
				{endDate}
			/>
		{/each}
	</ol>
</main>
