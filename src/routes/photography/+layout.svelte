<script lang="ts">
	let { children } = $props();
</script>

<main
	class="mx-auto flex max-w-5xl flex-col items-center justify-center justify-items-center p-4 font-mono"
>
	{@render children()}
</main>
