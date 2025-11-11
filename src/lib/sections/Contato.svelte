<script lang="ts">
    import { MapPin, Phone, Mail, Clock } from "@lucide/svelte";
    import { Button } from "$lib/components/ui/button";

    const contactInfo = [
        {
            icon: MapPin,
            title: "Localização",
            info: "Rua das Flores, 123 - Centro\nSão Paulo, SP",
        },
        {
            icon: Phone,
            title: "Telefone",
            info: "(11) 9999-9999\nWhatsApp disponível",
        },
        {
            icon: Mail,
            title: "E-mail",
            info: "contato@priscillasantiago.com.br",
        },
        {
            icon: Clock,
            title: "Horário",
            info: "Seg - Sex: 9h às 19h\nSáb: 9h às 14h",
        },
    ];
</script>

<section id="contato" class="py-24 bg-linear-to-b from-background to-muted/30">
    <div class="container mx-auto px-6">
        <div class="text-center mb-16 animate-fade-in">
            <p class="text-accent font-medium tracking-wider uppercase mb-4">
                Entre em Contato
            </p>
            <h2 class="text-4xl md:text-5xl font-playfair font-bold text-foreground mb-6">
                Agende sua consulta
            </h2>
            <p class="text-lg text-muted-foreground max-w-2xl mx-auto">
                Estamos prontos para atender você com todo cuidado e atenção que você merece
            </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-6xl mx-auto mb-12">
            {#each contactInfo as item, index}
                <div
                    class="text-center p-6 animate-fade-in-up"
                    style="animation-delay: {index * 100}ms;"
                >
                    <div class="inline-flex items-center justify-center w-16 h-16 rounded-full bg-linear-to-br from-accent/20 to-accent/10 mb-4 shadow-soft">
                        <item.icon class="w-7 h-7 text-accent" />
                    </div>
                    <h3 class="font-playfair font-semibold text-foreground mb-2">
                        {item.title}
                    </h3>
                    <p class="text-muted-foreground whitespace-pre-line text-sm leading-relaxed">
                        {item.info}
                    </p>
                </div>
            {/each}
        </div>

        <div class="text-center animate-scale-in" style="animation-delay: 400ms;">
            <Button
                size="lg"
                href="https://wa.me/5511999999999"
                target="_blank"
                class="bg-secondary hover:bg-secondary/90 text-secondary-foreground font-medium px-12 py-6 text-lg shadow-elegant transition-all hover:scale-105 hover:shadow-elegant/80"
            >
                Agendar pelo WhatsApp
            </Button>
        </div>
    </div>
</section>
