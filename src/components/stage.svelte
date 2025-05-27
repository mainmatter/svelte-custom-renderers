<script>
	let data =
		'Never gonna give you up, never gonna let you down\nNever gonna run around and desert you\nNever gonna make you cry, never gonna say goodbye\nNever gonna tell a lie and hurt you\nNever gonna give you up, never gonna let you down\nNever gonna run around and desert you\nNever gonna make you cry, never gonna say goodbye\nNever gonna tell a lie and hurt you'
			.split('')
			.map((c) => c.charCodeAt(0).toString(2).padStart(8, '0'))
			.join('')
			.split('');

	function rand() {
		return Math.floor(Math.random() * 12);
	}

	// Random bit flips
	// function flip(element) {
	// 	let on = (event) => {
	// 		if (Math.random < 0.5) {
	// 			return;
	// 		}
	// 		event.target.textContent = event.target.textContent === '1' ? '0' : '1';
	// 	};

	// 	element.addEventListener('animationiteration', on);

	// 	return () => {
	// 		element.removeEventListener('animationiteration', on);
	// 	}
	// }
</script>

<section>
	<div class="data" role="presentation" aria-hidden="true">
		{#each data as c, i (i)}
			<span class={`c${rand()}`}>{c}</span>
		{/each}
	</div>

	<code class="code"
		><pre>&lt;<span>script</span>&gt;
// ...
&lt;/<span>script</span>&gt;

&lt;Catalog&gt;
  &lt;List&gt;
    &lt;Image click=&quot;navigate()&quot; /&gt;
  &lt;/List&gt;
&lt;/Catalog&gt;

&lt;Toolbar /&gt;

&lt;style&gt;
  /* ... */
&lt;/style&gt;</pre></code
	>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
		overflow-x: hidden;
	}

	.data {
		grid-column: c1 / c6;
		grid-row: 1 / 3;
		mask: radial-gradient(closest-side, black 30%, transparent 100%);
		word-break: break-all;
		font-family: var(--font-mono);
		overflow: hidden;
		height: 24lh;
		-webkit-user-select: none;
		user-select: none;
		font-size: var(--fs-sm);
		line-height: 1.1;
	}

	.data span {
		margin: -0.5em;
		padding: 0.5em;
		--step: 0.5s;

		color: var(--bg);
		animation: blink calc(var(--step) * 12) infinite ease-in;
	}

	.data .c0 {
		animation-delay: calc(var(--step) * -11);
	}

	.data .c1 {
		animation-delay: calc(var(--step) * -9.1);
	}

	.data .c2 {
		animation-delay: calc(var(--step) * -9.2);
	}

	.data .c3 {
		animation-delay: calc(var(--step) * -8.3);
	}

	.data .c4 {
		animation-delay: calc(var(--step) * -7.4);
	}

	.data .c5 {
		animation-delay: calc(var(--step) * -6.5);
	}

	.data .c6 {
		animation-delay: calc(var(--step) * -5.6);
	}

	.data .c7 {
		animation-delay: calc(var(--step) * -4.7);
	}

	.data .c8 {
		animation-delay: calc(var(--step) * -3.8);
	}

	.data .c9 {
		animation-delay: calc(var(--step) * -2.9);
	}

	.data .c10 {
		animation-delay: calc(var(--step) * -1);
	}

	.data .c11 {
		animation-delay: 0;
	}

	@keyframes blink {
		0%,
		20%,
		80%,
		100% {
			color: var(--bg);
			text-shadow: 0 0 0.5em var(--bg);
		}
		50% {
			color: var(--fg-primary);
			text-shadow: 0 0 0.5em var(--fg-primary);
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.data span {
			animation: none;
		}
	}

	.code {
		position: relative;
		grid-column: leading / c2;
		grid-row: 1 / span 1;
		background: #23272f;
		margin-left: var(--grid-gutter);
		border: 1px solid #303541;
		box-shadow:
			0px 1px 2px rgba(0, 0, 0, 0.15),
			0px 2px 10px rgba(0, 0, 0, 0.15),
			0px 2px 40px rgba(0, 0, 0, 0.28);
		border-radius: var(--s-xs);
		font-size: 0.8125rem;
		line-height: 1.3;
		padding: var(--s-sm);
		overflow: hidden;
	}
</style>
