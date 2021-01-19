<script>
    import { setContext } from 'svelte';
	import { writable } from 'svelte/store';

	import Filter from './components/Filter.svelte';
	import Main from './components/Main.svelte';
	import Footer from './components/Footer.svelte';

	let filters = writable([]);
    setContext('filters', filters);
</script>

<Filter></Filter>
<Main></Main>
<Footer></Footer>

<!-- <style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
</style> -->