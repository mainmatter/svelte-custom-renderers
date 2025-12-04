<script>
	import Section from './section.svelte';

	let { children, title, supporters } = $props();
</script>

<Section {title}>
	{@render children()}

	<h3>Supporters</h3>

	<ul>
		{#each supporters as supporter (supporter.name)}
			<li>
				<a
					href={supporter.url}
					target="_blank"
					rel="noopener noreferrer nofollow"
					aria-label={supporter.name}
				>
					<supporter.logo />
				</a>
			</li>
		{/each}
	</ul>
</Section>

<style>
	ul {
		--logos-per-row: 2;

		display: flex;
		flex-flow: row wrap;
		justify-content: center;
		list-style: none;
		padding: 0;
		gap: var(--s-lg);
	}

	li {
		flex: 1 1 calc(100% / var(--logos-per-row));
		display: block;
		width: 100%;
		max-width: calc((100% / var(--logos-per-row) - var(--s-lg)) * (var(--logos-per-row) - 1));
	}

	li :global(svg) {
		width: 100%;
		height: auto;
	}
</style>
