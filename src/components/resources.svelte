<script>
	import IconExternal from '../icons/arrow-up-right-from-square.svelte';

	let { items } = $props();
</script>

<section>
	<h2>Resources</h2>

	<ul>
		{#each items as { href, title, description }, index (index)}
			<li>
				<a {href} target="_blank" rel="noopener noreferrer nofollow">{title}</a>
				{description}
				<IconExternal />
			</li>
		{/each}
	</ul>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
		background: var(--bg-muted);
		padding-block: var(--s-xl);
	}

	h2 {
		grid-column: c1 / c6;
		text-align: center;
		margin-bottom: var(--s-md);
	}

	ul {
		grid-column: c1 / c6;
		display: grid;
		gap: var(--s-sm);
		grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
		grid-template-rows: min-content 1fr;
		padding: 0;
	}

	li {
		position: relative;
		display: grid;
		grid-template-rows: subgrid;
		grid-row: span 2;
		gap: 0;
		padding: var(--s-sm);
		border: 2px solid #405063;
		border-radius: var(--s-xs);
		background: var(--bg);
		color: var(--fg-muted);
		box-shadow:
			0 0 0 rgba(0, 0, 0, 0.35),
			0 0 0 rgba(0, 0, 0, 0.35),
			0 0 0 rgba(0, 0, 0, 0.528);
		transition: all 0.2s ease;
	}

	a {
		display: block;
		color: var(--fg);
		text-decoration: none;
		font-weight: 700;
		padding-right: calc(1em + var(--s-sm));
		transition: all 0.2s ease;
	}

	li a:before {
		position: absolute;
		content: '';
		display: block;
		inset: 0;
	}

	li:has(a:hover) {
		background: var(--bg-muted);
		box-shadow:
			0px 0.0625rem 0.125rem rgba(0, 0, 0, 0.25),
			0px 0.125rem 0.625rem rgba(0, 0, 0, 0.25),
			0px 0.125rem 2.5rem rgba(0, 0, 0, 0.28);
	}

	li:has(a:hover) a {
		color: var(--primary);
	}

	li :global(svg) {
		position: absolute;
		top: var(--s-sm);
		right: var(--s-sm);
		width: 1em;
		height: 1em;
		vertical-align: baseline;
		color: var(--fg);
	}
</style>
