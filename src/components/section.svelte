<script>
	let { children, title } = $props();
</script>

<section>
	<div>
		{#if title}
			<h2>{title}</h2>
		{/if}

		{@render children()}
	</div>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
	}

	div {
		padding-block: calc(var(--s-2xl) / 2);
		text-align: center;
		grid-column: c2 / c5;
	}
</style>
