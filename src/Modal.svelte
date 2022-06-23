<script>
    let isShowModal = true;
    let isPromo = true;
</script>

{#if isShowModal}
    <div class="backdrop" class:promos={isPromo}>
        <div class="modal">
            <p>Signup for offer</p>
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
