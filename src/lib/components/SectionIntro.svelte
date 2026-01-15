<script>
	export let image;
	export let imageAlt = '';
	export let overlay = '';
	export let overlayColor = '';
	export let overlayPosition = '';
	export let title = '';
	export let text = '';
</script>

<section class="hero-section">
	<span class="hero">
		<img class="hero-img" src={image} alt={imageAlt} />

		<!-- Content that is conditionally rendered can be wrapped in an if block -->
		{#if overlay}
			<div class="image-overlay {overlayPosition}" style:color={overlayColor}>
				{overlay}
			</div>
		{/if}
	</span>
</section>

<section class="intro-section">
	<h1 class="page-name">{title}</h1>
	<p class="intro-text">{text}</p>
</section>

<style>
	.hero-section {
		display: grid;
		text-align: center;
		margin-top: 1.5rem;
	}

	.hero {
		position: relative;
	}

	.hero-img {
		width: 100%;
		border-radius: 1rem;
		max-height: 420px;
		object-fit: cover;
		object-position: center;
	}

	.image-overlay {
		position: absolute;
		top: 0.5rem;
		font-size: 2rem;
		font-family: 'Sacramento';
	}

	.image-overlay.left {
		left: 1rem;
		text-align: left;
	}

	.image-overlay.right {
		right: 1rem;
		text-align: right;
	}

	.intro-section {
		padding: 0;
	}

	h1 {
		font-size: 2rem;
		padding: 0 1rem;
	}

	.intro-text {
		font-size: 1.1rem;
		padding: 0 1rem;
		color: #403e3d;
	}
</style>
