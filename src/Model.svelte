<script>
    export let showModel = false // Step 4
    export let message //Dùng trong outside component
    let isPromo = true
</script>

{#if showModel} 
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="backdrop" class:promo={isPromo} on:click|self> 
    <!-- self rất quan trọng để khi nhấp trúng component nó không tự động thoát ra -->
    <div class="modal">
        <p>{message}</p>
    </div>
</div>
{/if}

<style>
    .backdrop{
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8);
    }
    .modal{
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background: white;
    }
    .promo .modal{
        background: rebeccapurple;
        color: white;
    }
</style>