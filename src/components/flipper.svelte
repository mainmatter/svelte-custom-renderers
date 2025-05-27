<script>
	import { onMount } from "svelte";

	function shuffle(array) {
		let i = array.length, j, temp;
		while (--i > 0) {
			j = Math. floor (Math. random () * (i + 1));
			temp = array[j];
			array[j] = array[i];
			array[i] = temp;
		}
		return array;
	}

	let { values } = $props();
	let previous = $state(1);
	let current = $state(0);
	let options = $derived(Array.isArray(values) ? values : (values ?? '').split(','));
	let randomizedOptions = $derived(shuffle(options));

	let start = new Date().getTime();

	function render() {
		let now = new Date().getTime();

		if (now - start > 1000) {
			let next = Math.floor(Math.random() * options.length);
			previous = current;
			current = next === previous ? ((next + 1) % randomizedOptions.length) : next;
			start = new Date().getTime();
		}

		requestAnimationFrame(render);
	};

	onMount(() => {
		requestAnimationFrame(render);
	});
</script>


<span class="flipper" data-flipper>
	{#each randomizedOptions as option, i (i)}
		<span class="option" data-current={i === current || null} data-previous={i === previous || null} aria-hidden={i > 0 ? true : null}>
			{option}
		</span>
	{/each}
</span>

<style>
	.flipper {
		display: inline-grid;
		text-align: left;
		font-family: var(--font-mono);
	}

	.option {
		display: block;
		grid-row: 1;
		grid-column: 1;
		opacity: 0;
		animation: out 0.5s ease forwards;
	}

	.option[data-current] {
		animation-name: in;
	}

	.option[data-previous] {
		animation-name: out;
	}

	@keyframes in {
		0% {
			transform: translateY(-100%);
			color: var(--bg-muted);
		}
		90%,100% {
			opacity: 1;
			transform: translateY(0);
			color: var(--fg-primary);
		}
	}

	@keyframes out {
		0%,10% {
			opacity: 1;
			transform: translateY(0);
			filter: blur(0em);
			color: var(--fg-primary);
		}
		100% {
			transform: translateY(100%);
			opacity: 0;
			filter: blur(0.25em);
			color: var(--bg-muted);
		}
	}
</style>
