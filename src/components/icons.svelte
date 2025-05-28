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
		display: flex;
		flex-wrap: wrap;
		list-style: none;
		padding: 0 0 0 var(--s-md);
		justify-items: center;
		gap: var(--s-md);
	}

	li {
		display: grid;
		align-items: center;
		justify-content: center;
		width: max(calc(20% - var(--s-md)), 6rem);
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
	}
</style>
