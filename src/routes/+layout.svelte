<script>
	import DesktopLayout from '$lib/DesktopLayout.svelte';
	import MobileLayout from '$lib/MobileLayout.svelte';
	import './styles.css';

	/**
	 * @type {number}
	 */
	let innerWidth;
</script>

<svelte:window bind:innerWidth={innerWidth} />

<div class="app">
	{#if innerWidth > 600}
		<DesktopLayout>
			<slot />
		</DesktopLayout>
	{:else}
		<MobileLayout>
			<slot />
		</MobileLayout>
	{/if}
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		position: fixed;
		top: 0px;
		left: 0px;
		right: 0px;
		bottom: 0px;
	}
</style>
