<!-- HomeGrid.svelte is responsible for content, passing props for each item and grid span -->

<script>
	import Card from '$lib/components/Card.svelte';

	// Array containing data
	let { items = [] } = $props();
</script>

<section class="cards-grid">
	{#each items as item}
		<div class="size size--{item.size}">
			<Card href={item.link} target="_blank" rel="noopener noreferrer">
				<img src={`/images/${item.image}`} alt={item.title} />

				<div class="card-content">
					<h3>{item.title}</h3>
					<p>{item.text}</p>
				</div>
			</Card>
		</div>
	{/each}
</section>

<style>
	.cards-grid {
		display: grid;
		grid-template-columns: repeat(12, 1fr);
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
		color: #272121;
	}

	p {
		margin: 0;
		color: #533535;
		line-height: 1.4;
	}

	img {
		width: 100%;
		object-fit: cover;
		display: block;
	}

	/* Grid span */
	.size--small {
		grid-column: span 3;
	}

	.size--medium {
		grid-column: span 6;
	}

	.size--large {
		grid-column: span 9;
	}

	/* Images sizes based on card size */
	.size--small img {
		height: 200px;
	}
	.size--medium img {
		height: 250px;
	}
	.size--large img {
		height: 300px;
	}

	/* Resposive Design */
	@media (max-width: 800px) {
		.size--small,
		.size--medium,
		.size--large {
			grid-column: span 6;
		}

		.size--small img,
		.size--medium img,
		.size--large img {
			height: 200px;
		}
	}

	@media (max-width: 550px) {
		.size--small,
		.size--medium,
		.size--large {
			grid-column: span 12;
		}
	}
</style>
