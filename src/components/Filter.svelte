<script>
    import { getContext } from 'svelte';

    let filters = getContext('filters');
</script>

<div class="filter">
    <p>{ $filters }</p>
</div>

<style>
	.filter {
        grid-row: 2 / 4;
        grid-column: center-start / center-end;
        
        background-color: var(--white);
        box-shadow: var(--shadow);
        border-radius: var(--border-radius);
    }
</style>