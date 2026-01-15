<!-- Card.svelte is responsible for card appearance and hover effects -->

<script>
	// In runes mod (Svelte 5), component props are declared with the $props rune
	let props = $props();
	let href = props.href ?? null;
</script>

<!-- The <svelte:element> element lets you render an element that is unknown at author time -->
<svelte:element this={href ? 'a' : 'article'} href={href || undefined} class="card">
	{@render props.children?.()}
</svelte:element>

<style>
	.card {
		display: flex;
		flex-direction: column;
		overflow: hidden;

		padding: 1rem;
		text-decoration: none;
		background: rgba(112, 105, 87, 0.1);
		border: 1px solid #e5e7eb;
		border-radius: 1rem;

		transition:
			transform 0.2s ease,
			box-shadow 0.2s ease;
	}

	.card:hover {
		transform: translateY(-4px);
		box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
	}
</style>
