<script>
	import Terminal from '../icons/rectangle-terminal.svelte';
	import Tablet from '../icons/tablet.svelte';
	import More from '../icons/wand-magic-sparkles.svelte';
	import WebGl from '../icons/cube.svelte';
	import PDF from '../icons/file-contract.svelte';

	let { children, title } = $props();
</script>

<section>
	<div>
		<h2>{title}</h2>
	</div>

	<ul>
		<li>
			<Terminal />
			<span>Terminal</span>
		</li>
		<li>
			<Tablet />
			<span>Native Apps</span>
		</li>
		<li>
			<PDF />
			<span>PDF</span>
		</li>
		<li>
			<WebGl />
			<span>WebGL</span>
		</li>
		<li>
			<More />
			<span>More</span>
		</li>
	</ul>

	<div>
		{@render children()}
	</div>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
		background-color: var(--bg-muted);
	}

	div {
		padding-block: var(--s-xl);
		text-align: center;
		grid-column: c2 / c5;
	}

	ul {
		grid-column: c1 / c6;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(7rem, 1fr));
		grid-template-rows: 1fr auto;
		list-style: none;
		padding: 0;
		gap: var(--s-md);
		justify-items: center;
	}

	li {
		grid-row: span 2;
		grid-template-rows: subgrid;
		display: grid;
		width: max(calc(20% - var(--s-md)), 6rem);
		gap: 0;
	}

	li :global(svg) {
		display: block;
		width: var(--s-xl);
		height: var(--s-xl);
		margin-inline: auto;
		color: var(--primary);
	}

	li span {
		display: block;
		margin-top: var(--s-sm);
		text-align: center;
		align-self: start;
	}
</style>
