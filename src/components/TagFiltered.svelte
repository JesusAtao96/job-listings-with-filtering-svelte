<script>
    import { getContext } from 'svelte';
    export let filterText;

    let filters = getContext('filters');

    function removeFilter(text) {
        $filters = $filters.filter(filter => filter !== text);
	}
</script>

<div class="tag-filtered">
    <span class="tag-filtered__text">{ filterText }</span>
    <button class="tag-filtered__btn" on:click={removeFilter(filterText)}>
        <svg class="tag-filtered__icon" xmlns="http://www.w3.org/2000/svg" width="14" height="14"><path fill="#FFF" fill-rule="evenodd" d="M11.314 0l2.121 2.121-4.596 4.596 4.596 4.597-2.121 2.121-4.597-4.596-4.596 4.596L0 11.314l4.596-4.597L0 2.121 2.121 0l4.596 4.596L11.314 0z"/></svg>
    </button>
</div>

<style>
	.tag-filtered {
        margin-right: 15px;
        margin-top: 10px;
        margin-bottom: 10px;
        background-color: var(--tag-background);
        display: flex;
        align-items: center;
        border-radius: 5px;
        overflow: hidden;
    }

	.tag-filtered:last-child {
        margin-right: 0;
    }

    .tag-filtered__text {
        color: var(--primary);
        font-size: .9rem;
        font-weight: 700;
        padding: 0 10px;
    }

    .tag-filtered__btn {
        background-color: var(--primary);
        border: 0;
        outline: 0;
        width: 32px;
        height: 32px;
        position: relative;
        cursor: pointer;
        transition: background-color .5s;
    }

    .tag-filtered__icon {
        position: absolute;
        left: 50%;
        right: 50%;
        transform: translate(-50%, -50%);
    }

    .tag-filtered__btn:hover {
        background-color: var(--black);
    }
</style>