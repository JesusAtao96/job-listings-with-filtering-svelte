<script>
	import Item from './Item.svelte';
</script>

<main>
    <Item></Item>
</main>

<style>
	main {
        grid-row: 4 / 5;
        grid-column: center-start / center-end;
        
        margin: 40px 0;
    }
</style>