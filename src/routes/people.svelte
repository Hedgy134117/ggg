<script>
	import { base } from '$app/paths';
	import reviews from '$lib/reviews.json';
	const people = Object.keys(reviews);
	const missing = ['Ivy', 'Arianna', 'Sam'];
</script>

<h1>PEOPLE</h1>
<div>
	{#each people as person}
		{#if missing.includes(person)}
			<p>{person}</p>
		{:else}
			<p><a href={base + '/' + person.toLowerCase() + '.pdf'} target="_blank">{person}</a></p>
		{/if}
	{/each}
</div>

<style>
	div {
		display: flex;
		justify-content: space-between;
	}

	p {
		font-size: 1.5em;
	}
</style>
