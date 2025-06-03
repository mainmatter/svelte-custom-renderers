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
</script>

<section role="presentation" aria-hidden="true">
	<div class="data">
		{#each data as c, i (i)}
			<span class={`c${rand()}`}>{c}</span>
		{/each}
	</div>
	<div class="float">
		<div class="raw">
			<span class="bar">&lt;List></span>
			<div>
				<span class="bar">&lt;Image</span><br />
				<span class="dot">&nbsp;</span><span class="dot">&nbsp;</span><span class="dot">&nbsp;</span
				>
			</div>
			<span class="bar">&lt;Toolbar></span>
		</div>

		<div class="source">
			<code class="code"
				><pre>&lt;<span class="tg">script</span>&gt;
  <span class="cm">// ...</span>
&lt;/<span class="tg">script</span>&gt;

&lt;<span class="tg">Catalog</span>&gt;
  &lt;<span class="tg">List</span>&gt;
    &lt;<span class="tg">Image</span> <span class="en">click</span><span class="kw">=</span><span
						class="st">&quot;</span
					><span class="fn">navigate</span>()<span class="st">&quot;</span> /&gt;
  &lt;/<span class="tg">List</span>&gt;
&lt;/<span class="tg">Catalog</span>&gt;

&lt;<span class="tg">Toolbar</span> /&gt;

&lt;<span class="tg">style</span>&gt;
  <span class="cm">/* ... */</span>
&lt;/<span class="tg">style</span>&gt;</pre></code
			>
		</div>

		<div class="tui">
			<pre class="code">Connected to SVELTE.shop

Welcome to Svelte Terminal UI!
Check out our catalog:

1 Shirt
2 Stickers
3 Socks
4 Paolo

0 Exit
</pre>
		</div>

		<div class="phone">
			<span></span><span></span><span></span><span></span>
		</div>

		<div class="browser">
			<span></span><span></span><span></span><span></span>
		</div>
	</div>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: subgrid;
		grid-column: leading / trailing;
	}

	section > div {
		position: relative;
		grid-column: 1 / -1;
		grid-row: 1 / span 1;
	}

	section > div > div {
		--scale: scale(min(calc(100vw / 1024px), 1));
		--delta: 0.5rem;

		transform: var(--scale);
		animation: float 15s linear infinite;
	}

	section > div > div:nth-child(2) {
		animation-delay: -1.5s;
	}

	section > div > div:nth-child(3) {
		animation-delay: -4s;
	}

	section > div > div:nth-child(4) {
		animation-delay: -6.3s;
	}

	@keyframes float {
		0%,
		100% {
			transform: var(--scale) translate(0, 0);
		}
		12.5% {
			transform: var(--scale) translate(calc(var(--delta) * 0.66), calc(var(--delta) * -0.66));
		}
		25% {
			transform: var(--scale) translate(calc(var(--delta) * 1), -calc(var(--delta) * -1));
		}
		37.5% {
			transform: var(--scale) translate(calc(var(--delta) * 1.66), calc(var(--delta) * -0.66));
		}
		50% {
			transform: var(--scale) translate(calc(var(--delta) * 2), 0);
		}
		62.5% {
			transform: var(--scale) translate(calc(var(--delta) * 1.66), calc(var(--delta) * 0.66));
		}
		75% {
			transform: var(--scale) translate(calc(var(--delta) * 1), calc(var(--delta) * 1));
		}
		87.5% {
			transform: var(--scale) translate(calc(var(--delta) * 0.33), calc(var(--delta) * 0.66));
		}
	}

	.data {
		mask: radial-gradient(closest-side, black 40%, transparent 100%);
		word-break: break-all;
		font-family: var(--font-mono);
		overflow: hidden;
		height: 22lh;
		-webkit-user-select: none;
		user-select: none;
		font-size: var(--fs-sm);
		line-height: 1.1;
		width: 100%;
		max-width: 76em;
		margin-inline: auto;
		box-shadow: inset 5px solid red;
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

	@keyframes blink {
		0%,
		20%,
		80%,
		100% {
			color: var(--bg);
			text-shadow: 0 0 0.5em var(--bg);
		}
		50% {
			color: var(--primary);
			text-shadow: 0 0 0.5em var(--primary);
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.data span {
			animation: none;
		}
	}

	.float {
		width: 100%;
		max-width: calc(var(--container) + 2 * var(--container-padding-inline));
		margin-inline: auto;
	}

	.code {
		display: block;
		position: relative;
		background: #23272f;
		border: 1px solid #303541;
		box-shadow:
			0px 0.0625rem 0.125rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 0.625rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 2.5rem rgba(0, 0, 0, 0.528);
		border-radius: var(--s-xs);
		font-size: 0.8125rem;
		line-height: 1.3;
		padding: var(--s-sm);
		overflow: hidden;
	}

	.code pre {
		color: #cccac2;
	}

	.code .tg {
		color: #5ccfe6;
	}

	.code .en {
		color: #73d0ff;
	}

	.code .kw {
		color: #ffad66;
	}

	.code .fn {
		color: #ffd173;
	}

	.code .st {
		color: #d5ff80;
	}

	.code .cm {
		color: #b8cfe680;
	}

	.source {
		position: absolute;
		top: 0.5rem;
		left: 0;
		z-index: 1;
	}

	.source .code {
		width: 38ch;
		justify-self: end;
	}

	.tui {
		position: absolute;
		top: 3rem;
		right: 17%;
		z-index: 2;
	}

	.tui .code {
		width: 40ch;
	}

	.raw {
		position: absolute;
		bottom: 1rem;
		left: 25%;
		z-index: 1;
		margin-left: var(--grid-gutter);
		grid-column: c2 / c6;
		grid-row: 1 / span 1;
		font-size: 0.75rem;
		font-family: var(--font-mono);
		animation: none;
	}

	.raw span {
		margin: 0 1em 0.5em 0;
		padding: 0.25em 0.5em;
		border-radius: 2em;
		display: inline-block;
		background: var(--primary);
	}

	.raw div {
		align-items: center;
		padding-left: calc(1lh + 0.5em);
	}

	.raw .bar {
		min-width: 15em;
	}

	.raw .dot {
		width: calc(1lh + 0.5em);
		height: calc(1lh + 0.5em);
	}

	.phone {
		overflow: hidden;
		position: absolute;
		top: 0;
		right: 1rem;
		z-index: 4;
		width: 12rem;
		height: 23rem;
		padding: 2.5rem 1rem 1rem 0.5rem;
		box-shadow:
			inset 0 0 0 0.0625rem #303541,
			inset 0 0 0 0.25rem #23272f,
			0px 0.0625rem 0.125rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 0.625rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 2.5rem rgba(0, 0, 0, 0.528);
		border-radius: 2rem;
		background: linear-gradient(180deg, #d7e5f5 0%, #ffffff 100%);
	}

	.phone:after {
		content: '';
		position: absolute;
		top: 0.85rem;
		left: calc(50% - 2rem);
		width: 4rem;
		height: 1rem;
		background: #23272f;
		border-radius: 1em;
		clear: both;
	}

	.phone:before,
	.phone span,
	.browser:before,
	.browser span {
		background: #d0d8e2;
		border-radius: 0.5rem;
	}

	.phone:before,
	.browser:before {
		content: '';
		position: absolute;
		bottom: 1.5rem;
		left: 1rem;
		right: 1rem;
		height: 2rem;
	}

	.phone span,
	.browser span {
		display: block;
		float: left;
		width: calc(50% - 0.5rem);
		padding-top: 50%;
		margin-left: 0.5rem;
		margin-bottom: 0.5rem;
	}

	.browser {
		position: absolute;
		bottom: 0;
		right: 8%;
		z-index: 3;
		width: 20rem;
		height: 14rem;
		padding: 5rem 6rem 0 0;
		box-shadow:
			inset 0 0 0 0.0625rem #303541,
			0px 0.0625rem 0.125rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 0.625rem rgba(0, 0, 0, 0.35),
			0px 0.125rem 2.5rem rgba(0, 0, 0, 0.528);
		border-radius: 1rem;
		background:
			radial-gradient(0.5rem at 1rem 1rem, var(--primary) 100%, transparent 100%),
			radial-gradient(0.5rem at 2.25rem 1rem, #d0d8e2 100%, transparent 100%),
			radial-gradient(0.5rem at 3.5rem 1rem, #d0d8e2 100%, transparent 100%),
			linear-gradient(180deg, #23272f 0%, #23272f 2rem, #d7e5f5 2rem, #ffffff 100%);
	}

	.browser span {
		padding-top: 4rem;
	}

	.browser:before {
		top: 2.5rem;
		left: 0.5rem;
		right: 0.5rem;
	}
</style>
