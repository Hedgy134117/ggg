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

    const halfStar = '<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ffa200}</style><path d="M288 0c-12.2 .1-23.3 7-28.6 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3L288 439.8V0zM429.9 512c1.1 .1 2.1 .1 3.2 0h-3.2z"/></svg>';
    const fullStar = '<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ffa200}</style><path d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z"/></svg>';
    function calculateStars(num) {
        if (isNaN(parseFloat(num))) {
            return num;
        }
        num = parseFloat(num);

        let res = '';
        for (let i = 0; i < Math.trunc(num); i++) {
            res += fullStar;
        }
        if (num % Math.trunc(num) == 0.5) {
            res += halfStar;
        }
        return res;
    }
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
            width: 200%;
        }
    }
</style>