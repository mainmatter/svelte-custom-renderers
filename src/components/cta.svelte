<script>
	import ArrowRight from '../icons/arrow-right.svelte';

	let { children, href = '#' } = $props();
</script>

<a {href}>{@render children()} <ArrowRight /></a>

<style>
	a {
		background: var(--primary);
		color: var(--fg);
		display: inline-flex;
		flex-flow: row nowrap;
		font-weight: bold;
		gap: var(--s-lg);
		padding: var(--s-sm) var(--s-md);
		text-decoration: none;
		white-space: nowrap;
		align-items: center;
		border-radius: var(--s-2xl);
	}

	a :global(svg) {
		height: 1lh;
		transform: translateX(0);
		transition: transform 0.5s ease;
	}

	a:is(:focus, :hover) :global(svg) {
		transform: translateX(var(--s-xs));
	}
</style>
