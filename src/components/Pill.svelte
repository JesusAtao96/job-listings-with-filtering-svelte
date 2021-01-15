<script>
    export let text;
    export let isNew;
    export let isFeatured;
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
        padding: 8px 10px 4px 10px;
        border-radius: 30px;
        color: var(--white);
        font-size: 11px;
        font-weight: 700;
        margin: 0 5px;
    }

    .pill--primary {
        background-color: var(--primary);
    }

    .pill--dark {
        background-color: var(--black);
    }
</style>