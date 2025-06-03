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
</style>
