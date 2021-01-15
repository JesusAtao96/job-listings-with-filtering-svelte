<script>
    export let text;
    export let hasSeparator;
</script>

<span class="detail { hasSeparator ? 'detail--separator' : '' }">{ text }</span>

<style>
	.detail {
        color: var(--dark-grayish-cyan);
        font-weight: 500;
    }

    .detail--separator {
        display: flex;
        align-items: center;
    }

    .detail--separator::before,
    .detail--separator::after {
        content: '';
        margin: 0 15px;
        width: 4px;
        height: 4px;
        border-radius: 100%;
        background-color: var(--dark-grayish-cyan);
    }
</style>