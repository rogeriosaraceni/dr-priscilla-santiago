<script>
    import { page } from '$app/state'; 
    import Button from '$lib/components/ui/button/button.svelte';
    import { MoveLeft } from '@lucide/svelte';
</script>

<main>
    <div class="container py-6">
        <div class="flex flex-col justify-center items-center">
            <h1 class="text-6xl mb-6">Erro {page.status}</h1>

            {#if page.error}
                {#if page.status === 404}
                    <h2 class="text-3xl">Página Não Encontrada</h2>
                    <p class="text-2x mb-6">A página que você tentou acessar ({page.url.pathname}) não existe.</p>
                {:else}
                    <h2 class="text-3xl">Erro do Servidor</h2>
                    <p class="text-2xl mb-6">Detalhes: {page.error?.message}</p>
                {/if}

            {:else}
                <p class="text-2xl mb-6">Um erro inesperado ocorreu. Tente novamente.</p>
            {/if}

            <Button>
                <MoveLeft /> <a href="/">Voltar para a Página Inicial</a>
            </Button>
        </div>
    </div>
</main>
