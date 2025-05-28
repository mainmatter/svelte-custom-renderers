<script>
	import End from '../components/end.svelte';
	import Help from '../components/help.svelte';
	import Top from '../components/top.svelte';

	import '../styles/main.css';

	let { children } = $props();
</script>

<Top />

{@render children()}

<Help />
<End />
