<script>
    export let data;

    import { calculateStars } from "./stars.js";

    let price = data[0];
    let flavor = data[1];
    let value = data[2];
    let ambiance = data[3];
    let favorite = data[4];
    let worst = data[5];

    let hasData = price == "AVG. PRICE" ? false : true;
</script>

<div class="outer" class:bottom={hasData} class:bolded={!hasData}>
    <div class="cell">
        <p>{#if hasData}${/if}{price}</p>
    </div>
    <div class="cell star">
        <p>{@html calculateStars(flavor)}</p>
    </div>
    <div class="cell star">
        <p>{@html calculateStars(value)}</p>
    </div>
    <div class="cell star">
        <p>{@html calculateStars(ambiance)}</p>
    </div>
    <div class="cell">
        <p>{favorite}</p>
    </div>
    <div class="cell">
        <p>{worst}</p>
    </div>
</div>

<style>
    .outer {
        display: grid;
        grid-template-columns: repeat(6, 1fr);

        border: 2px solid black;
        border-bottom: 0;
    }

    .cell {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 1em;

        border-right: 2px solid black;
    }

    .cell.star {
        padding: 0 !important;
    }

    .cell:last-of-type {
        border-right: 0;
    }

    .bottom {
        border-bottom: 2px solid black;
    }

    .bolded {
        font-weight: bold;
    }

    @media only screen and (max-width: 800px) {
        .outer {
            width: 250%;
        }
    }
</style>