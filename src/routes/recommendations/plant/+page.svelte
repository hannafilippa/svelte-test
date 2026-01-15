<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import CardsGrid from '$lib/components/CardsGrid.svelte';
	import plant from '$lib/images/cactus.jpg';

	export let data;
</script>

<SectionIntro
	image={plant}
	imageAlt="planta"
	overlay="för ett grönare liv"
	overlayColor="rgb(50, 112, 74)"
	overlayPosition="right"
	title="Rekommenderade växter"
	text="Ekologiska och närodlade växter utvalda med omsorg"
	textPosition="center"
/>

<CardsGrid items={data.plants} />
