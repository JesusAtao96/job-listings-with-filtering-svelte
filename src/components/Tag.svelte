<script>
    export let text;
</script>

<span class="tag">{ text }</span>

<style>
	.tag {
        color: var(--primary);
        background-color: var(--tag-background);
        font-weight: 700;
        padding: 7px 10px 5px 10px;
        margin-right: 15px;
        border-radius: 5px;
        cursor: pointer;
        transition: all .3s;
    }

    .tag:hover {
        background-color: var(--primary);
        color: var(--tag-background);
        transform: scale(1.1);
    }

    .tag:last-child {
        margin-right: 0;
    }
</style>