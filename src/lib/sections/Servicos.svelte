<script lang="ts">
  import { Card, CardContent } from "$lib/components/ui/card";
  import { Sparkles, Droplets, Zap, Star } from "@lucide/svelte";

  const services = [
    {
      icon: Sparkles,
      title: "Rejuvenescimento Facial",
      description:
        "Técnicas avançadas para revitalização e tonificação da pele facial, devolvendo o viço e a juventude natural.",
      color: "accent",
    },
    {
      icon: Droplets,
      title: "Drenagem Linfática",
      description:
        "Drenagem especializada para redução de edemas, melhora da circulação e desintoxicação corporal.",
      color: "secondary",
    },
    {
      icon: Zap,
      title: "Tratamentos Corporais",
      description:
        "Protocolos personalizados para modelagem corporal, redução de medidas e celulite.",
      color: "accent",
    },
    {
      icon: Star,
      title: "Pós-Operatório",
      description:
        "Acompanhamento especializado pós-cirúrgico para recuperação otimizada e resultados superiores.",
      color: "secondary",
    },
  ];
</script>

<section id="servicos" class="py-24 bg-linear-to-b from-background to-muted/30">
    <div class="container mx-auto px-6">
        <div class="text-center mb-16 animate-fade-in">
            <p class="text-accent font-medium tracking-wider uppercase mb-4">Nossos Serviços</p>

            <h2 class="text-4xl md:text-5xl font-playfair font-bold text-foreground mb-6">
                Tratamentos Especializados
            </h2>

            <p class="text-lg text-muted-foreground max-w-2xl mx-auto">
                Cada tratamento é cuidadosamente planejado para atender suas
                necessidades específicas
            </p>
        </div>

        <div class="grid md:grid-cols-2 gap-8 max-w-5xl mx-auto">
            {#each services as service}
                <Card class="border-none shadow-soft hover:shadow-elegant transition-all duration-500 hover:-translate-y-2 bg-card/80 backdrop-blur-sm animate-scale-in">
                    <CardContent class="p-8">
                        <div class="w-14 h-14 rounded-2xl flex items-center justify-center mb-6
                            {service.color === 'accent'
                            ? 'bg-linear-to-br from-accent/20 to-accent/10'
                            : 'bg-linear-to-br from-secondary/20 to-secondary/10'}"
                        >
                            <service.icon class="w-7 h-7 {service.color === 'accent' ? 'text-accent' : 'text-secondary'}"/>
                        </div>

                        <h3 class="text-2xl font-playfair font-semibold text-foreground mb-4">{service.title}</h3>
                        <p class="text-muted-foreground leading-relaxed">{service.description}</p>
                    </CardContent>
                </Card>
            {/each}
        </div>
    </div>
</section>
