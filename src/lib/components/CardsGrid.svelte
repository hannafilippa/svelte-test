<!-- CardsGrid.svelte is responsible for content, passing props for each item and grid span -->

<script>
	import Card from '$lib/components/Card.svelte';

	// Array containing  link, size, image, title and text
	let { items = [] } = $props();
</script>

<section class="cards-grid">
	{#each items as item (item.id)}
		<!--<div class="grid-item">-->
		<Card href={item.link}>
			<img src={`/images/${item.image}`} alt={item.title} />

			<div class="card-content">
				<h3>{item.title}</h3>
				<p>{item.text}</p>

				{#if item.price}
					<div class="card-footer">
						<p class="price">{item.price} kr</p>
						<button class="btn">Köp här</button>
					</div>
				{/if}
			</div>
		</Card>
		<!--</div>-->
	{/each}
</section>

<style>
	.cards-grid {
		display: grid;
		grid-template-columns: repeat(4, 3fr);
		gap: 1.5rem;
	}

	/*
	.grid-item {
	grid-column: span 3;
	}
	*/

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

	/* If item price */
	.card-footer {
		display: flex;
		align-items: center;
		padding-top: 1rem;
	}

	.btn {
		margin-left: auto;
		border-radius: 1rem;
		border: 0;
		padding: 0.6rem;

		text-decoration: none;
		background: rgba(51, 27, 15, 0.7);
		color: white;
	}

	.btn:hover {
		color: black;
		background: rgba(51, 27, 15, 0.2);
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
</style>
