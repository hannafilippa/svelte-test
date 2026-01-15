<script>
	import CardsGrid from '$lib/components/CardsGrid.svelte';
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import coffee from '$lib/images/coffee-bag-big.jpg';

	export let data;
</script>

<SectionIntro
	image={coffee}
	imageAlt="påse med kaffebönor"
	overlay="från böna till kopp"
	overlayColor="rgb(201, 170, 148)"
	overlayPosition="right"
	title="Kaffeprodukter"
	text="Ekologiskt, hållbart och noggrant utvalt kaffe"
	textPosition="center"
/>

<CardsGrid items={data.coffees} />
