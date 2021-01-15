<script>
	import Pill from './Pill.svelte';
    import Tag from './Tag.svelte';

    export let data;

    console.log(data);
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
            <span class="item__detail">{ data.postedAt }</span>
            <span class="item__detail item__detail--separator">{ data.contract }</span>
            <span class="item__detail">{ data.location }</span>
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
        grid-template-columns: 20px min-content 1fr min-content 25px;
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
    }

    .item__details {
        display: flex;
        align-items: center;
    }

    .item__detail {
        color: var(--dark-grayish-cyan);
        font-weight: 500;
    }

    .item__detail--separator {
        display: flex;
        align-items: center;
    }

    .item__detail--separator::before,
    .item__detail--separator::after {
        content: '';
        margin: 0 15px;
        width: 4px;
        height: 4px;
        border-radius: 100%;
        background-color: var(--dark-grayish-cyan);
    }

    .item__tags {
        grid-column: 4 / 5;

        display: flex;
    }
</style>