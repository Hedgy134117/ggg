<script>
    // @ts-nocheck
    import reviews from "$lib/reviews.json";
    import results from "$lib/results.json";
    import Review from './review.svelte';
    import Header from './header.svelte';
	import Result from "./result.svelte";
    let names = Object.keys(reviews);
    let places = ["The Joint Coffee Co", "Bitty & Beau's Coffee", "Billy's Downtown Diner", "Hotel B Ice Cream Parlor", "Chocolate Lab"]
</script>

<Header />
{#each places as place, i}
    <div class="place">
        <h1>{place}</h1>
        <Review name="NAME" bolded=true data={["PRODUCT", "PRICE", "FLAVOR", "VALUE", "AMBIANCE", "COMMENTS"]} />
        {#each names as name}
            <Review name={name} data={reviews[name][i]} />
        {/each}
        <br />
        <Result data={["AVG. PRICE", "AVG. FLAVOR", "AVG. VALUE", "AVG. AMBIANCE", "FAVORITE", "LEAST FAVORITE"]} />
        <Result data={results[place]} />
    </div>
{/each}

<style>
    :global(body) {
        width: 80%;
        margin: 0 auto;
        background-color: #ffe5b4;
        font-family: 'Imprima', sans-serif;
    }

    :global(p) {
        margin: 0;
    }

    .place {
        margin-bottom: 3em;
        overflow: auto;
    }

    .place h1 {
        font-size: 3em;
        text-align: center;
        text-transform: uppercase;
        font-style: italic;
    
        position: sticky;
        left: 0;
    }

    @media only screen and (max-width: 1300px) {
        :global(body) {
            width: 100%;
        }
    }
</style>