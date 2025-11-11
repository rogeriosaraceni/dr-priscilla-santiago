<script lang="ts">
	import { Instagram, Facebook, Mail } from '@lucide/svelte';

	let links = [
		{ label: "Sobre", url: "#sobre" },
		{ label: "Serviços", url: "#servicos" },
		{ label: "Depoimentos", url: "#depoimentos" },
		{ label: "Contato", url: "#contato" }
	];

	let midias = [
		{ label: "Instagram", icon: Instagram, url: "https://www.instagram.com/" },
		{ label: "Facebook", icon: Facebook, url: "https://www.facebook.com/" },
		{ label: "E-mail", icon: Mail, url: "mailto:contato@exemplo.com" }
	]
</script>

<footer class="footer text-zinc-100 py-12">
	<div class="container mx-auto px-6">
		<div class="mb-8 grid gap-8 md:grid-cols-3">
			<div>
				<h3 class="font-playfair mb-4 text-2xl font-bold">Dra. Priscilla Santiago</h3>
				<p class="text-sm leading-relaxed">
					Especialista em Fisioterapia Dermato-Funcional, dedicada a proporcionar excelência em tratamentos estéticos.
				</p>
			</div>

			<div>
				<h4 class="font-playfair mb-4 font-semibold">Links Rápidos</h4>
				<ul class="space-y-2 text-sm">
					{#each links as link}
						<li>
							<a href={link.url} class="hover:text-zinc-300 transition-colors">{link.label}</a>
						</li>
					{/each}
				</ul>
			</div>

			<div>
				<h4 class="font-playfair mb-4 font-semibold">Redes Sociais</h4>
				<div class="flex gap-4">
					{#each midias as midia}
						<a
							href={midia.url}
							target="_blank"
							rel="noopener noreferrer"
							class="bg-zinc-300/10 hover:bg-stone-300/20 flex items-center justify-center h-10 w-10 rounded-full transition-all hover:scale-110"
							aria-label={midia.label}
						>
							<midia.icon class="h-5 w-5" />
						</a>
					{/each}
				</div>
			</div>
		</div>

		<div class="border-zinc-50/10 text-primary-foreground/60 border-t pt-8 text-center text-sm">
			<p>
				&copy; {new Date().getFullYear()} Dra. Priscilla Santiago. Todos os direitos reservados.
			</p>
		</div>
	</div>
</footer>

<style>
	.footer{
		background-color:#38332e;
	}
</style>
