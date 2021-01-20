<script>
    import { getContext } from 'svelte';
    import TagFiltered from './TagFiltered.svelte';

    let filters = getContext('filters');

    function clearFilters() {
        $filters = [];
	}
</script>

<div class="filter { $filters.length > 0 && 'filter--show'}">
    <div class="filter__container">
        {#each $filters as filter}
            <TagFiltered filterText={ filter } />
        {/each}
    </div>
    <div class="filter__clear" on:click={clearFilters}>Clear</div>
</div>

<style>
	.filter {
        grid-row: 2 / 4;
        grid-column: center-start / center-end;

        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 10px 40px;
        background-color: var(--white);
        box-shadow: var(--shadow);
        border-radius: var(--border-radius);
        margin: auto;
        width: 0;
        height: 0;
        opacity: 0;
        transition: all .4s ease-out;
    }

    .filter--show {
        opacity: 1;
        width: 100%;
        height: 100%;
    }

    .filter__container {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
    }

    .filter__clear {
        color: var(--primary);
        font-size: .9rem;
        cursor: pointer;
        padding: 10px;
    }

    .filter__clear:hover {
        font-weight: 700;
        text-decoration: underline;
    }
</style>