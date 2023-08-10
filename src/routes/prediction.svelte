<script>
    // @ts-nocheck
    export let question;
    export let data;
    export let bottom;

    import { calculateStars } from "./stars";

    let sorted = [];
    for (let name in data) {
        sorted.push([name, data[name]])
    }
    sorted.sort((a, b) => b[1] - a[1]); // Descending order
</script>

<div class="prediction">
    <h1>{question}</h1>
    {#each sorted as result, i}
    <div class="result" class:bottom-border={bottom}>
        <p>{result[0]}</p>
        <p>{@html calculateStars(result[1])}</p>
    </div>
    {/each}
</div>

<style>
    h1 {
        font-size: 1.8em;
    }

    p {
        padding: 0.5em;
    }

    .prediction {
        border: 1px solid black;
        border-bottom: 0;
    }

    .result {
        display: grid;
        grid-template-columns: 1fr 1fr;

        border-top: 1px solid black;
    }

    .result p:first-child {
        border-right: 1px solid black;
    }

    .bottom-border:last-of-type {
        border-bottom: 1px solid black;
    }
</style>