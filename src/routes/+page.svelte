<script>
    // @ts-nocheck
    import reviews from "$lib/reviews.json";
    let names = Object.keys(reviews);
</script>

{#each names as name}
    <h1>{name}</h1>
    {#each reviews[name] as review}
        <li>{review}</li>
    {/each}
{/each}