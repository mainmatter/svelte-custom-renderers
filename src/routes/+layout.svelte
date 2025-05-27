<script>
	import End from '../components/end.svelte';
	import Sponsor from '../components/sponsor.svelte';
	import Top from '../components/top.svelte';

	import '../styles/main.css';

	let { children } = $props();
</script>

<Top />

{@render children()}

<Sponsor />
<End />
