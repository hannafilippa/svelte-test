<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import HomeGrid from '$lib/components/HomeGrid.svelte';
	import hero from '$lib/images/lake-hero.jpg';

	export let data;
</script>

<SectionIntro
	image={hero}
	imageAlt="Bänk vid en sjö"
	overlay="Välkommen"
	overlayColor="rgb(64, 46, 42)"
	overlayPosition="left"
	title="Från naturen till ditt hem"
	text="En inspirationssida för dig som vill leva mer hållbart i vardagen. Här hittar du hållbart utvalda produkter och inspiration för en mer medveten och grön vardag. Med fokus på kvalitet, lång livslängd och schyssta val. Upptäck hur små förändringar kan göra stor skillnad i din vardag. På vår sida hittar du
		inspirerande artiklar och produkter som hjälper dig leva mer hållbart och medvetet. Starta dagen
		med en kopp nymalda kaffebönor från ekologiska gårdar eller skapa ett lugnare och grönare hem
		med våra utvalda växter. Låt dig inspireras till en mer medveten, grön livsstil."
/>

<div class="intro-menu">
	<h4>Utforska vad vår sida har att erbjuda just dig</h4>
</div>

<HomeGrid items={data.pages} />

<style>
	.intro-menu {
		text-align: center;
	}
</style>
