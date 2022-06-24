<script>
    let message = "default value";
    let showModal = false;
    let isPromo = false;
    export { message, isPromo, showModal };
</script>

{#if showModal}
    <div class="backdrop" class:promos={isPromo} on:click|self>
        <div class="modal">
            <p>{message}</p>
            <slot></slot>
            <slot name="title"></slot>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }
    .modal {
        padding: 10px;
        border-radius: 5px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background-color: white;
    }
    .promos .modal {
        background: crimson;
        color: white;
    }
</style>
