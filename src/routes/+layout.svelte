<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<title>Dra. Priscilla Santiago | Fisioterapia Dermato-Funcional</title>
	<meta
		name="description"
		content="Especialista em Fisioterapia Dermato-Funcional. Tratamentos estéticos avançados com excelência e cuidado personalizado."
	/>
	<meta name="author" content="Dra. Priscilla Santiago" />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap"
		rel="stylesheet"
	/>

	<meta property="og:title" content="Dra. Priscilla Santiago | Fisioterapia Dermato-Funcional" />
	<meta
		property="og:description"
		content="Especialista em Fisioterapia Dermato-Funcional. Tratamentos estéticos avançados com excelência e cuidado personalizado."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:image" content="https://lovable.dev/opengraph-image-p98pqg.png" />
</svelte:head>

<div class="flex min-h-screen flex-col">
	<main class="m-auto flex w-full flex-1 flex-col bg-zinc-100">
		{@render children()}
	</main>

	<Footer />
</div>
