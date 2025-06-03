<script>
	import Cta from './cta.svelte';
</script>

<section>
	<div>
		<h2>Need Svelte Support?</h2>

		<p>Mainmatter is here to empower your team to succeed with Svelte in your projects.</p>
		<p>
			We offer a comprehensive range of Svelte and SvelteKit workshops, covering everything from
			foundational concepts to advanced techniques. Our experts also collaborate closely with teams
			already using Svelte—accelerating development, solving complex challenges, and providing
			hands-on mentoring directly within your projects.
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
		border-radius: 0;
	}
</style>
