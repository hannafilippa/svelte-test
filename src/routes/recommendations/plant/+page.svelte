<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import CardsGrid from '$lib/components/CardsGrid.svelte';
	import plant from '$lib/images/plant.jpg';

	export let data;
</script>

<SectionIntro
	image={plant}
	imageAlt="planta"
	overlay="för ett grönare liv"
	overlayColor="rgb(223,206,170)"
	overlayPosition="left"
	title="Rekommenderade växter"
	text="En inspirationssida för dig som vill omge dig med grönska som gör gott. Här samlar vi noggrant utvalda och rekommenderade växter – med fokus på miljönytta, bättre inomhusluft och ökat välmående. Oavsett om du söker lättskötta krukväxter, luftrenande sorter eller växter som skapar lugn, vill vi guida dig till grönare val.

Upptäck växter som bidrar till ett hälsosammare hem och en mer hållbar vardag, och låt naturen bli en naturlig del av ditt liv."
/>

<CardsGrid items={data.plants} />
