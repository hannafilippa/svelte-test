<script>
	import CardsGrid from '$lib/components/CardsGrid.svelte';
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import coffee from '$lib/images/coffee-cup-hero.jpg';
	import soap from '$lib/images/coffee-scrub.jpg';

	export let data;
</script>

<SectionIntro
	image={coffee}
	imageAlt="påse med kaffebönor"
	overlay="från böna till kopp"
	overlayColor="rgb(201, 170, 148)"
	overlayPosition="right"
	title="Kaffeprodukter"
	text="Vår inspirationssida för dig som uppskattar riktigt bra kaffe. Här samlar vi noggrant utvalda och rekommenderade kaffesorter – med fokus på kvalitet, ekologi och hållbara val. Oavsett om du föredrar ljusrostat, mörkrostat eller specialkaffe vill vi guida dig till bättre kaffeupplevelser. Upptäck kaffe med omtanke om både människa och natur, och hitta nya favoriter att njuta av i din vardag."
/>

<CardsGrid items={data.coffees} />

<section class="article">
	<img class="article-img" src={soap} alt="kaffesump blir exklusiv skrubb" />
	<div class="article-text">
		<h3>Här blir kaffesump exklusiv skrubb</h3>
		<h5>
			I Sverige konsumerar vi nästan 8 kilo kaffe per person varje år. Två ton kaffesump som annars
			skulle kasserats har blivit skönhetsprodukter sedan 2021. I Malmö återvinns kaffesump, havre
			och olja till skönhetsindustrin. Läs mer på Aftonbladet
		</h5>
		<a
			href="https://www.aftonbladet.se/skonhet/a/0V8bbB/kaffesump-atervinns-till-skonhetsprodukt"
			target="_blank">TILL ARTIKELN →</a
		>
	</div>
</section>

<style>
	/* Category-section */
	.article {
		display: flex;
		flex-direction: row;
		gap: 1rem;
		margin: 1rem;
		border-top: solid #c2afa0;
	}

	.article-img {
		border: 1px solid #ddd;
		border-radius: 4px;
		margin-top: 1rem;
		padding: 0.5rem;
		max-width: 200px;
		max-height: 200px;
	}

	.article-text {
		inline-size: 40rem;
	}

	a {
		padding: 0.5rem;
		font-size: 0.8rem;

		text-decoration: none;
		background: #c2afa0;
		color: black;
	}

	a:hover {
		color: green;
	}

	@media (max-width: 550px) {
		.article {
			flex-direction: column;
		}

		.article-text {
			inline-size: auto;
		}

		h3 {
			margin: 0;
		}
	}
</style>
