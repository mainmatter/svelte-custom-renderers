<script>
	import IconExternal from '../icons/arrow-up-right-from-square.svelte';
	import Logo from '../icons/logo.svelte';
</script>

<header>
	<h1>
		<Logo />
	</h1>
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
		grid-column: leading / trailing;
		padding-block: var(--s-xl);
		font-size: var(--fs-sm);
	}

	h1 {
		grid-column: c1 / c3;
	}

	a {
		color: #fff;
	}

	nav {
		grid-column: c4 / c6;
		display: flex;
		justify-content: flex-end;
		align-items: end;
	}

	ul {
		display: flex;
		justify-content: flex-end;
		gap: var(--s-lg);
	}

	nav :global(svg) {
		height: 1em;
		color: #9eb8d8;
	}

	nav a {
		display: flex;
		align-items: center;
		gap: var(--s-xs);
	}
</style>
