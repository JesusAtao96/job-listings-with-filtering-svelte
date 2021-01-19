<script>
	import Detail from './Detail.svelte';
	import Pill from './Pill.svelte';
    import Tag from './Tag.svelte';

    export let job;
</script>

<div class="item">
    <img class="item__logo" src={ job.logo } alt={ job.company }>

    <div class="item__information">
        <div class="item__header">
            <span class="item__company">{ job.company }</span>

            <div class="item__pills">
                <Pill text='New!' isNew={ job.new } />
                <Pill text='Featured' isFeatured={ job.featured } />
            </div>
        </div>

        <span class="item__position">{ job.position }</span>

        <div class="item__details">
            <Detail text={ job.postedAt } />
            <Detail text={ job.contract } hasSeparator={ true } />
            <Detail text={ job.location } />
        </div>
    </div>

    <div class="item__tags">
        <Tag text={ job.role } />
        <Tag text={ job.level } />
        {#each job.languages as language}
            <Tag text={ language } />
        {/each}
        {#each job.tools as tool}
            <Tag text={ tool } />
        {/each}
    </div>
</div>

<style>
	.item {
        background-color: var(--white);
        box-shadow: var(--shadow);
        border-radius: var(--border-radius);

        border-left: 5px solid var(--primary);
        height: 150px;

        display: grid;
        grid-template-columns: 20px min-content 1fr 1fr 25px;
        grid-template-rows: 30px min-content 30px;
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
        font-size: 0.9rem;
        font-weight: 700;
        margin-right: 10px;
    }

    .item__pills {
        display: flex;
        align-items: center;
    }

    .item__position {
        font-weight: 700;
        font-size: 1.2rem;
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

    @media only screen and (max-width: 900px) {
        .item {
            height: auto;

            grid-template-columns: 20px 1fr 20px;
            grid-template-rows: 0px 50px repeat(6, min-content);
            column-gap: 0px;
        }

        .item__logo {
            grid-column: 2 / 3;
            grid-row: 1 / 2;
            width: 75px;
        }

        .item__information {
            grid-column: 2 / 3;
            grid-row: 3 / 4;
        }

        .item__information::after {
            content: '';
            width: 100%;
            height: 1px;
            background-color: var(--dark-grayish-cyan);
            margin: 15px 0;
        }

        .item__position {
            margin: 15px 0;
            font-size: 1.1rem;
        }

        .item__tags {
            grid-column: 2 / 3;
            grid-row: 4 / 5;
            justify-content: flex-start;
            margin-bottom: 20px;
        }
    }

    @media only screen and (max-width: 600px) {
        .item {
            grid-template-rows: 0px 35px repeat(6, min-content);
        }
        
        .item__logo {
            width: 50px;
        }
    }
</style>