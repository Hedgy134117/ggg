<script>
    // @ts-nocheck
    import reviews from "$lib/reviews.json";
    import Review from './review.svelte';
    import Header from './header.svelte';
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
    </div>
{/each}
<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M293.3 .6c10.9 2.5 18.6 12.2 18.6 23.4V408.7c0 8.9-4.9 17-12.7 21.2L151 509.1c-8.1 4.3-17.9 3.7-25.3-1.7s-11.2-14.5-9.7-23.5l26.2-155.6L31.1 218.2c-6.5-6.4-8.7-15.9-5.9-24.5s10.3-14.9 19.3-16.3l153.2-22.6L266.3 13.5c4.9-10.1 16.1-15.4 27-12.9zM263.9 128.4l-28.6 58.8c-3.5 7.1-10.2 12.1-18.1 13.3L99 217.9 184.9 303c5.5 5.5 8.1 13.3 6.8 21L171.4 443.7l92.5-49.4V128.4z"/></svg>

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