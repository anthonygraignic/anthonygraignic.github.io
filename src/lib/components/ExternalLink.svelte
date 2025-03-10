<script lang="ts">
	import Icon from '@iconify/svelte';

	export let url;
	export let newTab = true;
</script>

<a
	href={url}
	rel="external nofollow noreferrer"
	target={newTab ? '_blank' : '_self'}
	class="inline-flex items-center text-center underline"
>
	<slot></slot>
	<Icon icon="mdi:external-link" />
</a>
