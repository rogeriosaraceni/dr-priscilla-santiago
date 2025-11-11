<script lang="ts">
    import { ArrowUp } from "@lucide/svelte";
    import { onMount } from "svelte";

    let visible = $state(false);

    const checkScroll = () => {
        visible = window.scrollY > 400;
    };

    const scrollToTop = () => {
        window.scrollTo({
            top: 0,
            behavior: "smooth",
        });
    };

    onMount(() => {
        window.addEventListener("scroll", checkScroll);
        return () => window.removeEventListener("scroll", checkScroll);
    });
</script>

{#if visible}
    <button
        onclick={scrollToTop}
        aria-label="Voltar ao topo"
        class="cursor-pointer fixed bottom-8 right-8 z-50 p-3 rounded-full bg-secondary/90 hover:bg-secondary text-secondary-foreground shadow-elegant hover:shadow-elegant/80 backdrop-blur-sm transition-all duration-300 hover:scale-110 hover:-translate-y-1 animate-fade-in"
    >
        <ArrowUp class="w-6 h-6" strokeWidth={2} />
    </button>
{/if}

<style>
    @keyframes fade-in {
        from { opacity: 0; transform: translateY(10px); }
        to   { opacity: 1; transform: translateY(0); }
    }
    .animate-fade-in {
        animation: fade-in 0.4s ease-out forwards;
    }
</style>
