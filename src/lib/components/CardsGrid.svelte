<!-- CardsGrid.svelte is responsible for content, passing props for each item and grid span -->

<script>
	import Card from '$lib/components/Card.svelte';

	// Array containing  link, image, title and text
	let { items = [] } = $props();
</script>

<section class="cards-grid">
	{#each items as item (item.id)}
		<Card href={item.link}>
			<img src={`/images/${item.image}`} alt={item.title} />

			<div class="card-content">
				<h3>{item.title}</h3>
				<p>{item.text}</p>
			</div>
		</Card>
	{/each}
</section>

<style>
	.cards-grid {
		display: grid;
		grid-template-columns: repeat(4, 3fr);
		gap: 1.5rem;
	}

	/* Styling props */
	.card-content {
		display: flex;
		flex-direction: column;
		padding-top: 0.5rem;
	}

	h3 {
		margin-top: 0;
		font-size: 1.25rem;
		color: #272121;
	}

	p {
		margin: 0;
		color: #533535;
		line-height: 1.4;
	}

	img {
		width: 100%;
		height: 200px;
		aspect-ratio: 4/3;
		object-fit: cover;
		display: block;
	}

	/* Responsive Layout */
	@media (max-width: 800px) {
		.cards-grid {
			grid-template-columns: repeat(3, 4fr);
		}
	}

	@media (max-width: 550px) {
		.cards-grid {
			grid-template-columns: repeat(2, 6fr);
		}
	}

	@media (max-width: 450px) {
		.cards-grid {
			grid-template-columns: repeat(1, 12fr);
		}
	}
</style>
