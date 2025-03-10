<script>
	export let isLastElement = false;
	export let logo;
	export let title;
	export let subtitle;

	export let startDate;
	export let endDate;
</script>

<li class="flex w-full">
	<div class="flex shrink-0 flex-col items-center">
		{#if logo}
			<img src={logo} alt="{title} logo" class="h-12 w-12 shrink-0 rounded-full" />
		{:else}
			<div class="h-12 w-12 shrink-0 rounded-full bg-gray-50 dark:bg-gray-800"></div>
		{/if}
		{#if isLastElement}
			<div class="w-[2px] grow bg-gray-200 dark:bg-gray-700"></div>
		{/if}
	</div>
	<div class="ml-3 flex grow flex-col pb-14">
		<div class="flex h-12 w-full items-center justify-between">
			<div class="flex flex-col items-start justify-start">
				<div class="text-primary font-semibold md:text-xl">
					{title}
				</div>
				<div class="text-faint text-xs md:text-sm">
					{subtitle}
				</div>
			</div>
			<div
				class="ml-2 flex items-center text-xs text-gray-500 md:ml-8 md:text-sm dark:text-gray-400"
			>
				{#if endDate}
					{@const duration = `${new Date(startDate).toLocaleString('default', { month: 'short', year: 'numeric' })}
                - ${new Date(endDate).toLocaleString('default', { month: 'short', year: 'numeric' })}`}
					{duration}
				{:else}
					<div
						class="mr-2 h-1.5 w-1.5 animate-pulse rounded-full border-green-700 bg-green-600"
					></div>
					Present
				{/if}
			</div>
		</div>
	</div>
</li>
