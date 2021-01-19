<script>
    export let text = '';
    export let isNew = false;
    export let isFeatured = false;
</script>

{#if isNew}
    <span class="pill pill--primary" >{ text }</span>
{/if}

{#if isFeatured}
    <span class="pill pill--dark" >{ text }</span>
{/if}

<style>
	.pill {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 6px 8px 2px 8px;
        border-radius: 30px;
        color: var(--white);
        font-size: 0.7rem;
        font-weight: 700;
        margin: 0 5px;
        text-transform: uppercase;
    }

    .pill--primary {
        background-color: var(--primary);
    }

    .pill--dark {
        background-color: var(--black);
    }
</style>