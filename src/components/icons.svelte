<script>
	import Terminal from '../icons/rectangle-terminal.svelte';
	import Tablet from '../icons/tablet.svelte';

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
		padding-block: calc(var(--s-2xl) / 2);
		text-align: center;
		grid-column: c2 / c5;
	}

  ul {
    grid-column: c1 / c6;
  	display: grid;
    grid-auto-flow: column;
    grid-auto-columns: minmax(max-content, 1fr);
   	list-style: none;
    padding: 0;
  }

  li {
  	display: flex;
    flex-flow: column;
		align-items: center;
  }


  li :global(svg) {
  	max-width: var(--s-xl);
   	color: var(--fg-primary);
  }

  li span {
    display: block;
    margin-top: var(--s-sm);
  }
</style>
