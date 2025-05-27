<script>
	let { children, title } = $props();

</script>

<section>
	{#if title}
		<h2>{title}</h2>
	{/if}

	{@render children()}
</section>

<style>
	section {
		padding-block: calc(var(--s-2xl) / 2);
		text-align: center;
		grid-column: c3 / c6;
	}
</style>
