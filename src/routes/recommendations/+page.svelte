<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import CardsGrid from '$lib/components/CardsGrid.svelte';
	import cafe from '$lib/images/shop.jpg';
	import finale from '$lib/images/jars.jpg';

	export let data;
</script>

<SectionIntro
	image={cafe}
	title="Våra rekommendationer - produkter utvalda med omsorg"
	text="Hållbart utvalda produkter för en grönare vardag. Fokus på kvalitet, lång livslängd och schyssta val. Allt för hjälpa dig ta ett steg i rätt riktning med både naturen och din egen hälsa i centrum."
/>

<CardsGrid items={data.recommendations} />

<img src={finale} alt="hängande vaser" class="finale-image" />

<section class="quote">
	<h2>Live simply so others may simply live</h2>
	<p>- Mahatma Gandhi</p>
</section>

<style>
	.finale-image {
		width: 100%;
		border-radius: 1rem;
		margin-top: 2rem;
	}

	.quote {
		background: rgba(188, 146, 83, 0.3);
		padding: 0.5rem;
		margin: 1rem;
		border-radius: 2rem;
		text-align: center;
	}
</style>
