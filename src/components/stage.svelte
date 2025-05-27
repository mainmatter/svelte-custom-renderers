<script>
	let code = 'Never gonna give you up, never gonna let you down\nNever gonna run around and desert you\nNever gonna make you cry, never gonna say goodbye\nNever gonna tell a lie and hurt you\nNever gonna give you up, never gonna let you down\nNever gonna run around and desert you\nNever gonna make you cry, never gonna say goodbye\nNever gonna tell a lie and hurt you'.split('').map((c) => c.charCodeAt(0).toString(2).padStart(8, '0')).join('').split('');

	function rand() {
		return Math.floor(Math.random() * 11);
	}
</script>

<section>
	<div class="code">
		{#each code as c, i (i)}
			<span class={`c${rand()}`}>{c}</span>
		{/each}
	</div>
</section>

<style>
	section {
		grid-column: 1 / -1;
	}

	.code {
		word-break: break-all;
		font-family: var(--font-mono);
	}

	span {
		margin: -0.5em;
		padding: 0.5em;
		--step: 0.5s;

		color: var(--bg);
		animation: blink calc(var(--step) * 12) infinite ease-in;
	}

	.c0 {
		animation-delay: calc(var(--step) * -11);
	}

	.c1 {
		animation-delay: calc(var(--step) * -10);
	}

	.c2 {
		animation-delay: calc(var(--step) * -9);
	}

	.c3 {
		animation-delay: calc(var(--step) * -8);
	}

	.c4 {
		animation-delay: calc(var(--step) * -7);
	}

	.c5 {
		animation-delay: calc(var(--step) * -6);
	}

	.c6 {
		animation-delay: calc(var(--step) * -5);
	}

	.c7 {
		animation-delay: calc(var(--step) * -4);
	}

	.c8 {
		animation-delay: calc(var(--step) * -3);
	}

	.c9 {
		animation-delay: calc(var(--step) * -2);
	}

	.c10 {
		animation-delay: calc(var(--step) * -1);
	}

	.c11 {
		animation-delay: 0;
	}

	@keyframes blink {
		0%, 20%, 80%, 100% {
			color: var(--bg);
			text-shadow: 0 0 0.5em var(--bg);
		}
		50% {
			color: var(--fg-primary);
			text-shadow: 0 0 0.5em var(--fg-primary);
		}
	}
</style>
