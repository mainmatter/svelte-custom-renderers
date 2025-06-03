<script>
	import ogImage from '../assets/og_image.jpg';

	let { title, description, url } = $props();
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />

	<meta property="og:url" content="https://{url}" />
	<meta property="og:type" content="website" />
	<meta property="og:image" content={ogImage} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:image" content={ogImage} />
	<meta property="twitter:domain" content={url} />
	<meta property="twitter:url" content="https://{url}" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
</svelte:head>
