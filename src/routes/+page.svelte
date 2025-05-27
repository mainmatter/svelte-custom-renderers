<script>
	import Flipper from "../components/flipper.svelte";
	import Section from "../components/section.svelte";
	import Stage from "../components/stage.svelte";
</script>

<Stage />

<Section>
	<h2>
		Render to <Flipper values={['Anything','Native','Canvas','Markdown','PDF','Terminal','Text','Unicorns','WebGL']} />
	</h2>

	<p>
		Use Svelte without the DOM! The Svelte Renderer API allows you to use Svelte Components anywhere – not just your browser.
	</p>
	<p>
		From fully native apps to server-rendered graphics or even non-visual use cases, the Renderer API opens the door to entirely new platforms.
	</p>
</Section>

<Section title="Beyond the browser">
	<p>
		Build new things using your favorite developer experience. Wherever you can define how elements are created, updated, and destroyed — you can now run Svelte.
	</p>
</Section>
