<script lang="ts">
	import { GraduationCap, Award, Heart} from '@lucide/svelte';

	const credentials = [
		{
			icon: GraduationCap,
			title: 'Formação',
			description: 'Especialização em Fisioterapia Dermato-Funcional'
		},
		{
			icon: Award,
			title: 'Experiência',
			description: 'Mais de 10 anos dedicados à estética avançada'
		},
		{
			icon: Heart,
			title: 'Filosofia',
			description: 'Cuidado integral e resultados naturais'
		}
	];
</script>

<section id="sobre" class="bg-card py-24">
	<div class="container mx-auto px-6">
		<div class="grid items-center gap-16 md:grid-cols-2">
			<div class="animate-fade-in">
				<p class="mb-4 font-medium tracking-wider text-accent uppercase">Sobre a Dra. Priscilla</p>
				<h2 class="font-playfair mb-6 text-4xl leading-tight font-bold text-foreground md:text-5xl">Excelência e dedicação em cada tratamento</h2>
				<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
					Com uma abordagem personalizada e técnicas de ponta, a Dra. Priscilla Santiago se dedica a proporcionar resultados excepcionais, sempre respeitando a
					individualidade de cada paciente.
				</p>
				<p class="text-lg leading-relaxed text-muted-foreground">
					Sua expertise em Fisioterapia Dermato-Funcional combina conhecimento científico com sensibilidade estética, garantindo tratamentos eficazes e seguros.
				</p>
			</div>

			<div class="grid animate-scale-in gap-6">
				{#each credentials as credential}
					<div class="shadow-soft hover:shadow-elegant rounded-2xl bg-background p-8 transition-all duration-300 hover:-translate-y-1">
						<div class="flex items-start gap-4">
							<div class="rounded-xl bg-linear-to-br from-accent/20 to-accent/10 p-3">
								<credential.icon class="w-6 h-6 text-accent"/>
							</div>
							<div>
								<h3 class="font-playfair mb-2 text-xl font-semibold text-foreground">{credential.title}</h3>
								<p class="text-muted-foreground">{credential.description}</p>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
