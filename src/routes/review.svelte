<script>
    // @ts-nocheck
    export let name;
    export let data;
    export let bolded = false;

    let product = data[0];
    let price = data[1];
    let flavor = data[2];
    let value = data[3];
    let ambiance = data[4];
    let comments = data[5];

    let lastRow = name == "Westley" ? true : false;
</script>

<div class:bottom={lastRow} class:bolded={bolded} class="outer">
    <div class="cell">
        <p class="">{name}</p>
    </div>
    <div class="cell">
        <p class="">{product}</p>
    </div>
    <div class="cell">
        <p class="">{price}</p>
    </div>
    <div class="cell">
        <p class="">{flavor}</p>
    </div>
    <div class="cell">
        <p class="">{value}</p>
    </div>
    <div class="cell">
        <p class="">{ambiance}</p>
    </div>
    <div class="cell">
        <p>{comments}</p>
    </div>
</div>

<style>
    .outer {
        display: grid;
        grid-template-columns: 10% 15% 7% 7% 7% 7% 47%;

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

    @media only screen and (max-width: 1300px) {
        .outer {
            grid-template-columns: 10% 15% 10% 10% 10% 10% 35%;
        }
    }

    @media only screen and (max-width: 800px) {
        .outer {
            width: 200%;
        }
    }
</style>