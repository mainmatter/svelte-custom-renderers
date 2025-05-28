<script>
	import ArrowRight from '../icons/arrow-right.svelte';
	import Cta from './cta.svelte';
</script>

<section>
	<div>
		<h2>Need help building?</h2>

		<p>
			Mainmatter is here to empower your team to fully realize those benefits in your web and
			backend projects.
		</p>
		<p>
			Getting started with Svelte and SvelteKit is straightforward but an experienced partner can
			help ensure you're set up for success from the beginning.
		</p>

		<p>
			<Cta href="https://mainmatter.com/svelte-consulting/">Learn more</Cta>
		</p>
	</div>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
		background: #6200ee;
	}

	div {
		padding-block: var(--s-xl);
		grid-column: c1 / c6;
	}

	p {
		max-width: 32em;
	}

	p :global(a) {
		background: #02ceba;
		color: #fff;
	}
</style>
