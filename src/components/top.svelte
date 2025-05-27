<script>
	import IconExternal from '../icons/arrow-up-right-from-square.svelte';
</script>

<header>
	<h1>Svelte Renderer API</h1>
	<nav>
		<ul>
			<li><a href="/">Announcement <IconExternal /></a></li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: c1 / c8;
		padding-block: var(--s-xl);
	}

	h1 {
		grid-column: c1 / c2;
	}

	a {
		color: #fff;
	}

	nav {
		grid-column: c3 / c8;
		display: flex;
		justify-content: flex-end;
		align-items: center;
	}

	ul {
		display: flex;
		justify-content: flex-end;
		gap: var(--s-lg);
	}

	nav :global(svg) {
		height: 1em;
		fill: #9EB8D8;
	}

	nav a {
		display: flex;
		align-items: center;
		gap: var(--s-xs);
	}
</style>
