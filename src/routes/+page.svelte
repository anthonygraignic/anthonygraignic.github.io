<script lang="ts">
	import Icon from '@iconify/svelte';
	const email = 'firstname.lastname.fr@gmail.com';
</script>

<svelte:head>
	<title>Anthony Graignic</title>
	<meta name="description" content="Anthony Graignic is on the Internet." />
</svelte:head>

<main class="flex flex-col items-center justify-center justify-items-center p-4 font-mono">
	<div class="mt-16 flex flex-col items-center justify-center justify-items-center">
		<h1 class="text-center text-5xl font-bold md:text-justify">Anthony Graignic</h1>

		<img
			src="/12660783.png"
			alt="A pixellised man with glasses"
			class="mt-8 max-w-32 hover:animate-pulse"
		/>
	</div>

	<p class="mt-16"></p>

	<div class="mt-16 grid grid-cols-5 items-center justify-items-center gap-3 text-4xl">
		<a
			href="mailto:{email}"
			target="_blank"
			rel="external nofollow noreferrer"
			on:click={() => alert(`Email me at ${email}`)}
		>
			<Icon icon="mdi:email-outline">Email</Icon>
		</a>
		<a href="https://gitlab.com/anthonygraignic" target="_blank" rel="external nofollow noreferrer"
			><Icon icon="mdi:gitlab">Gitlab</Icon></a
		>
		<a href="https://github.com/anthonygraignic" target="_blank" rel="external nofollow noreferrer"
			><Icon icon="mdi:github">GitHub</Icon></a
		>
		<a href="https://x.com/agraignic" target="_blank" rel="external nofollow noreferrer"
			><Icon icon="ri:twitter-x-line">X</Icon></a
		>
		<a
			href="https://www.linkedin.com/in/anthonygraignic/"
			target="_blank"
			rel="external nofollow noreferrer"><Icon icon="mdi:linkedin">LinkedIn</Icon></a
		>
	</div>
</main>
