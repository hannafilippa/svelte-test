<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import HomeGrid from '$lib/components/HomeGrid.svelte';

	import article from '$lib/images/article.jpg';

	export let data;
</script>

<SectionIntro
	image={article}
	imageAlt="Gammeldagsskrivare"
	text="Välkommen till vår samling av artiklar - här hittar du inspiration, tips och guider för en mer hållbar vardag. Från små förändringar i hemmet till medvetna val i vardagen. Vi vill göra det enkelt att följa med och hitta idéer som verkligen fungerar."
/>

<HomeGrid items={data.articles} />
