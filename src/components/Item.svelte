<script>
	import Detail from './Detail.svelte';
	import Pill from './Pill.svelte';
    import Tag from './Tag.svelte';

    export let data;
</script>

<div class="item">
    <img class="item__logo" src={ data.logo } alt={ data.company }>

    <div class="item__information">
        <div class="item__header">
            <span class="item__company">{ data.company }</span>

            <div class="item__pills">
                <Pill text='New' isNew={ data.new } />
                <Pill text='Featured' isFeatured={ data.featured } />
            </div>
        </div>

        <span class="item__position">{ data.position }</span>

        <div class="item__details">
            <Detail text={ data.postedAt } />
            <Detail text={ data.contract } hasSeparator={ true } />
            <Detail text={ data.location } />
        </div>
    </div>

    <div class="item__tags">
        <Tag text={ data.role } />
        <Tag text={ data.level } />
        {#each data.languages as language}
            <Tag text={ language } />
        {/each}
    </div>
</div>

<style>
	.item {
        background-color: var(--white);
        box-shadow: var(--shadow);
        border-radius: var(--border-radius);

        border-left: 5px solid var(--primary);

        display: grid;
        grid-template-columns: 20px min-content 1fr 1fr 25px;
        grid-template-rows: 25px min-content 25px;
        column-gap: 20px;
        align-items: center;
    }

    .item__logo,
    .item__information,
    .item__tags {
        grid-row: 2 / 3;
    }

    .item__logo {
        grid-column: 2 / 3;
    }

    .item__information {
        grid-column: 3 / 4;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100%;
    }

    .item__header {
        display: flex;
        align-items: center;
    }

    .item__company {
        color: var(--primary);
        font-weight: 700;
        margin-right: 10px;
    }

    .item__pills {
        display: flex;
        align-items: center;
    }

    .item__position {
        font-weight: 700;
        font-size: 18px;
        transition: color .3s;
    }

    .item__position:hover {
        color: var(--primary);
    }

    .item__details {
        display: flex;
        align-items: center;
    }

    .item__tags {
        grid-column: 4 / 5;

        display: flex;
        justify-content: flex-end;
        flex-wrap: wrap;
    }
</style>