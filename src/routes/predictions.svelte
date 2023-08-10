<script>
    // @ts-nocheck
    import predictions from "$lib/predictions.json";
    import Prediction from "./prediction.svelte";
    let questions = Object.keys(predictions);
</script>

<h1>Predictions</h1>
<div class="predictions">
    {#each questions as question, i}
        <Prediction question={question} data={predictions[question]} bottom={i == 3} />
    {/each}
</div>


<style>
    .predictions {
        
    }
</style>