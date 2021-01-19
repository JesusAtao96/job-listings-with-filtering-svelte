<script>
    import { getContext } from 'svelte';

    export let text;

    let filters = getContext('filters');

    function addFilter(text) {
        if($filters.indexOf(text) === -1 ) {
            $filters = [...$filters, text];
        }
	}
</script>

<span class="tag" on:click={addFilter(text)}>{ text }</span>

<style>
	.tag {
        color: var(--primary);
        background-color: var(--tag-background);
        font-weight: 700;
        padding: 7px 10px 5px 10px;
        margin: 5px 15px 5px 0;
        border-radius: 5px;
        cursor: pointer;
        transition: all .3s;
        font-size: 0.86rem;
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