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
		padding-block: var(--s-xl);
		text-align: center;
		grid-column: c2 / c5;

		:global {
			p + h3 {
				margin-top: var(--s-xl);
			}
		}
	}
</style>
