<script>
    import Item from './Item.svelte';

    import * as json from '../data.json'
    
    console.log(json.default);
</script>

<main>
    {#each json.default as data}
        <Item data={ data }></Item>
    {/each}
</main>

<style>
	main {
        grid-row: 4 / 5;
        grid-column: center-start / center-end;
        
        margin: 40px 0;
        display: grid;
        gap: 25px;
    }
</style>