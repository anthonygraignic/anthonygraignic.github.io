<script lang="ts">
	import { onMount } from 'svelte';

	let showBitMask = false;
	let isAnimated = false;

	onMount(() => {
		// Show the possibilities
		enableBitMaskAfterDelay(12000);
	});

	function enableBitMaskAfterDelay(ms = 12000) {
		const timer = setTimeout(() => {
			if (showBitMask) {
				return;
			}
			showBitMask = true;

			startAnimationSampleAfterDelay(1000);
			stopAnimationSampleAfterDelay(5000);
		}, ms);

		return () => {
			clearTimeout(timer);
		};
	}

	function startAnimationSampleAfterDelay(ms = 1000) {
		const timeout = setTimeout(() => {
			isAnimated = true;
		}, ms);
		return () => clearTimeout(timeout);
	}
	function stopAnimationSampleAfterDelay(ms = 2000) {
		const timeout = setTimeout(() => {
			isAnimated = false;
		}, ms);
		return () => clearTimeout(timeout);
	}

	const cols = 21;
	const rows = 21;
	const step = 12;
	const totalDuration = 12;
	const totalBits = cols * rows;
	const interval = totalDuration / totalBits;

	const messageBits = [
		0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0,
		0, 1, 0, 0, 1, 1, 1, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 1, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0,
		0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1,
		0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 1,
		0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0,
		0, 1, 0, 0, 1, 1, 1, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 1, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0,
		0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1,
		0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 1
	];
	// Repeat the message bits to fill the grid
	const gridBits = Array.from({ length: totalBits }, (_, i) => messageBits[i % messageBits.length]);
</script>

<div
	role="img"
	aria-label="A pixellised man with glasses"
	on:mouseenter={() => {
		showBitMask = true;
		isAnimated = true;
	}}
	on:mouseleave={() => (isAnimated = false)}
	on:touchstart={() => {
		showBitMask = true;
		isAnimated = true;
		stopAnimationSampleAfterDelay(4000);
	}}
	style="width: 252px; height: 252px;"
>
	<svg viewBox="0 0 252 252" width="252" height="252" xmlns="http://www.w3.org/2000/svg">
		<defs>
			<mask id="bitMask" maskUnits="userSpaceOnUse" x="0" y="0" width="252" height="252">
				<rect width="252" height="252" class="mask-rect" />
				<g>
					{#each Array(rows) as _, rowIndex}
						{#each Array(cols) as _, colIndex}
							{@const i = rowIndex * cols + colIndex}
							{@const delay = i * interval}
							{@const x = colIndex * step + 6}
							{@const y = rowIndex * step + 12}
							{@const isOne = gridBits[i] === 1}
							<text {x} {y} class="bit" opacity="0.4">
								{isOne ? '1' : '0'}
								{#if isAnimated}
									<animate
										attributeName="opacity"
										values={isOne ? '0;1;0' : '1;0;1'}
										dur="2s"
										begin={delay + 's'}
										repeatCount="indefinite"
									/>
								{/if}
							</text>
						{/each}
					{/each}
				</g>
			</mask>
		</defs>

		<image
			href="/12660783-2.png"
			width="252"
			height="252"
			mask={showBitMask ? 'url(#bitMask)' : undefined}
		/>
	</svg>
</div>
