<script lang="ts">
	import { onMount } from 'svelte';
	import { Button } from '$lib/components/ui/button/index.js';

  	let scrollY = $state(0);

  	function handleScroll() {
    	scrollY = window.scrollY;
 	}

  	onMount(() => {
    	window.addEventListener('scroll', handleScroll);
    	return () => window.removeEventListener('scroll', handleScroll);
  	});
</script>

<section class="relative flex h-screen items-center justify-center overflow-hidden">
	<div class="parallax absolute inset-0" style="transform: translateY({scrollY * 0.5}px);">
		<img src="hero.jpg" alt="Dra. Priscilla Santiago" class="h-full w-full object-cover" />
		<div class="absolute inset-0 bg-linear-to-b from-background/70 via-background/50 to-background"></div> 
	</div>

	<div class="animate-fade-in-up relative z-10 container mx-auto px-6 text-center">
		<div class="mx-auto max-w-4xl">
			<p class="animate-fade-in mb-4 font-medium tracking-wider text-accent uppercase">Fisioterapia Dermato-Funcional</p>
			<h1 class="font-playfair mb-6 text-5xl leading-tight font-bold text-foreground md:text-7xl">Dra. Priscilla Santiago</h1>
			<p class="mx-auto mb-8 max-w-2xl text-xl font-light text-muted-foreground md:text-2xl">
				Excelência em tratamentos estéticos com técnicas avançadas e cuidado personalizado
			</p>
			<div class="flex flex-wrap justify-center gap-4">
				<Button class={`bg-accent/60 hover:bg-accent/70 text-accent-foreground font-medium px-8 py-6 text-lg shadow-elegant hover:scale-105`}>
					<a href="#contato">Agendar Consulta</a>
				</Button>

				<Button variant="outline" class={`border-2 border-secondary-1 text-secondary hover:bg-secondary hover:text-white font-medium px-8 py-6 text-lg hover:scale-105`}>
					<a href="#servicos">Conheça os Serviços</a>
				</Button>
			</div>
		</div>
	</div>

	<div class="animate-float absolute bottom-8 left-1/2 -translate-x-1/2 transform">
		<div class="flex h-10 w-6 justify-center rounded-full border-2 border-accent/50 p-2">
			<div class="h-3 w-1 rounded-full bg-accent/70"></div>
		</div>
	</div>
</section>
