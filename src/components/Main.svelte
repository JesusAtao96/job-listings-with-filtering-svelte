<script>
    import { getContext, onDestroy } from 'svelte';

    import Item from './Item.svelte';

    import * as json from '../data.json'
    
    let jobs = json.default;

    let filters = getContext('filters');

    const unsubscribe = filters.subscribe(value => {
        jobs = $filters.length > 0 ? filterJobs(jobs) : jobs;
        console.log('jobs', jobs);
    });

    function filterJobs(jobs) {
        return jobs.filter((job) => {
            let tags = [job.role, job.level, ...job.languages, ...job.tools];
            return $filters.every((value) => tags.includes(value));
        });
    }

    onDestroy(unsubscribe);
</script>

<main>
    {#each jobs as job}
        <Item job={ job }></Item>
    {:else}
        <p>No jobs found!</p>
    {/each}
</main>

<style>
	main {
        grid-row: 4 / 5;
        grid-column: center-start / center-end;

        margin: 40px 0;
        display: grid;
        grid-template-rows: repeat(auto-fit, minmax(150px, min-content));
        column-gap: 25px;
        row-gap: 65px;
    }

    @media only screen and (max-width: 900px) {
        main {
            grid-row: 5 / 6;

            grid-template-columns: repeat(auto-fit, minmax(325px, 1fr));
            grid-template-rows: min-content;
        }
    }

    @media only screen and (max-width: 600px) {
        main {
            grid-template-columns: 1fr;
            grid-template-rows: min-content;
        }
    }
</style>