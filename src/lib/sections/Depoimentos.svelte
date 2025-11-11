<script lang="ts">
    import { Card, CardContent } from "$lib/components/ui/card";
    import { Quote } from "@lucide/svelte";

    const depoimentos = [
        {
            name: "Maria Silva",
            text: "Profissional excepcional! Os resultados superaram minhas expectativas. A Dra. Priscilla é extremamente atenciosa e dedicada.",
            rating: 5,
        },
        {
            name: "Ana Costa",
            text: "Ambiente acolhedor e tratamento personalizado. Me senti cuidada em cada detalhe. Recomendo de olhos fechados!",
            rating: 5,
        },
        {
            name: "Juliana Oliveira",
            text: "Depois de pesquisar muito, encontrei a profissional ideal. Técnica impecável e resultados naturais e harmoniosos.",
            rating: 5,
        },
    ];

    const stars = (rating: number) => Array.from({ length: rating });
</script>

<section id="depoimentos" class="py-24 bg-card">
    <div class="container mx-auto px-6">
        <div class="text-center mb-16 animate-fade-in">
            <p class="text-secondary font-medium tracking-wider uppercase mb-4">Depoimentos</p>
            <h2 class="text-4xl md:text-5xl font-playfair font-bold text-foreground mb-6">O que dizem nossos pacientes</h2>
        </div>

        <div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
            {#each depoimentos as depoimento, index}
                <Card
                    class="border-none shadow-soft hover:shadow-elegant transition-all duration-500 hover:-translate-y-2 bg-background animate-scale-in"
                    style="animation-delay: {index * 150}ms;"
                >
                    <CardContent class="p-8">
                        <Quote class="w-10 h-10 text-accent/30 mb-4" strokeWidth={1.5} />

                        <p class="text-muted-foreground mb-6 leading-relaxed italic">"{depoimento.text}"</p>

                        <div class="flex items-center justify-between">
                            <p class="font-playfair font-semibold text-foreground">{depoimento.name}</p>

                            <div class="flex gap-1">
                                {#each stars(depoimento.rating) as _}
                                    <span class="text-accent text-lg leading-none">★</span>
                                {/each}
                            </div>
                        </div>
                    </CardContent>
                </Card>
            {/each}
        </div>
    </div>
</section>
