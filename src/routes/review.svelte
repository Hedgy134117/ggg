<script>
    // @ts-nocheck
    export let name;
    export let data;
    export let bolded = false;

    import { calculateStars } from "./stars.js";

    let product = data[0];
    let price = data[1];
    let flavor = data[2];
    let value = data[3];
    let ambiance = data[4];
    let comments = data[5];

    let lastRow = name == "Westley" ? true : false;
</script>

<div class:bottom={lastRow} class:bolded={bolded} class="outer">
    <div class="cell bolded">
        <p class="">{name}</p>
    </div>
    <div class="cell">
        <p class="">{product}</p>
    </div>
    <div class="cell">
        <p class="">{#if !bolded}${/if}{price}</p>
    </div>
    <div class="cell star">
        <p class="">{@html calculateStars(flavor)}</p>
    </div>
    <div class="cell star">
        <p class="">{@html calculateStars(value)}</p>
    </div>
    <div class="cell star">
        <p class="">{@html calculateStars(ambiance)}</p>
    </div>
    <div class="cell">
        <p>{comments}</p>
    </div>
</div>

<style>
    .outer {
        display: grid;
        grid-template-columns: 10% 15% 10% 10% 10% 10% 35%;

        border: 1px solid black;
        border-bottom: 0;
    }

    .cell {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 1em;

        border-right: 1px solid black;
    }

    .cell.star {
        padding: 0 !important;
    }

    .cell:first-of-type {
        background-color: #ffe5b4;
        left: 0;
        position: sticky;
    }
    
    .cell:last-of-type {
        border-right: 0;
    }

    .bottom {
        border-bottom: 1px solid black;
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