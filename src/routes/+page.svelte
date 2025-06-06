<script>
	import Cta from '../components/cta.svelte';
	import Flipper from '../components/flipper.svelte';
	import Icons from '../components/icons.svelte';
	import Meta from '../components/meta.svelte';
	import Resources from '../components/resources.svelte';
	import Section from '../components/section.svelte';
	import Stage from '../components/stage.svelte';
</script>

<Meta
	title="Custom Renderers for Svelte, a Mainmatter Initiative"
	description="Help us enable cross-platform UI development with Svelte for endless possibilities."
	url="svelte-custom-renderers.com"
/>

<Stage />

<Section>
	<h2>
		Render to <Flipper
			values={[
				'Anything',
				'Native',
				'Canvas',
				'Markdown',
				'PDF',
				'Terminal',
				'Text',
				'Unicorns',
				'WebGL'
			]}
		/>
	</h2>

	<p>
		Custom Svelte renderers unlock the ability to use Svelte beyond the browser. This enables
		organizations to use the same technology across platforms like the web as well as native apps.
	</p>
	<p>
		With custom renderers, teams can reuse UI code across different output formats, streamlining
		development and ensuring consistency wherever a user interface is needed.
	</p>
</Section>

<Icons title="Endless Possibilities">
	<p>
		Once the foundation for custom renderers is in place, the possibilities are endless. Beyond web
		and native apps, Svelte can power renderers for PDFs, video generation, terminal UIs, WebGL
		canvases, and more. This opens the door to a wide ecosystem of renderer-specific tooling and
		innovation—all while keeping Svelte at the core of your UI development.
	</p>
</Icons>

<Section title="Support the Project">
	<p>
		Mainmatter has built a working prototype that proves this is not just an idea—it’s feasible and
		already functional.
	</p>
	<p>
		But getting from prototype to a robust, production-ready foundation takes time and effort. If
		your company is excited about the potential of using Svelte across all your platforms, we invite
		you to sponsor the project. Your support will help us finish the implementation and make it
		stable, well-documented, and ready for everyone to use.
	</p>
	<p>
		<Cta
			href="https://mainmatter.notion.site/20664e58ddfa80a38291f605a0e229b3"
			target="_blank"
			rel="noopener noreferrer nofollow">Get in Touch</Cta
		>
	</p>
</Section>

<Resources
	items={[
		{
			href: 'https://mainmatter.com/blog/2025/05/22/native-apps-with-svelte/',
			title: 'Announcement Blog Post',
			description: "Read Paolo Ricciuti's blog post announcing the project and its goals."
		},
		{
			href: 'https://github.com/mainmatter/svelte-lynx-integration',
			title: 'POC: Svelte + Lynx',
			description:
				"GitHub repository for Paolo Ricciuti's proof-of-concept for building native apps using Lynx through Svelte."
		}
	]}
/>
