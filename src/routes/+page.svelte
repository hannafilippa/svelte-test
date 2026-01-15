<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import HomeGrid from '$lib/components/HomeGrid.svelte';

	import hero from '$lib/images/lake-hero.jpg';
	import coffee from '$lib/images/coffee-cup-hero.jpg';
	import soaps from '$lib/images/coffee-scrub.jpg';

	export let data;
</script>

<!-- welcome back ,cookies text 
 https://svelte.dev/tutorial/kit/cookies
 -->

<SectionIntro
	image={hero}
	imageAlt="Bänk vid en sjö"
	overlay="Välkommen"
	overlayColor="rgb(64, 46, 42)"
	overlayPosition="left"
	title="Green & Grounded"
	text="En inspirationswebbsida för dig som vill leva mer hållbart i vardagen. Här hittar du hållbart utvalda produkter och inspiration för en mer medveten och grön vardag. Med fokus på kvalitet, lång livslängd och schyssta val."
	textPosition="center"
/>

<section class="cards">
	<section class="card">
		<img class="card-img" src={coffee} alt="kaffekopp" />
		<div class="card-overlay">
			<h4 class="card-text">Starta dagen med en kopp nymalda kaffebönor från ekologiska gårdar</h4>
			<a href="/recommendations/coffee" class="btn">TILL SIDAN</a>
		</div>
	</section>

	<section class="card">
		<img class="card-img" src={soaps} alt="kaffesump blir exklusiv skrubb" />
		<div class="card-overlay">
			<h4 class="card-text black-text">
				I Malmö återvinns kaffesump, havre och olja till skönhetsindustrin
			</h4>
			<!-- I Sverige konsumerar vi nästan 8 kilo kaffe per person varje år. Två ton kaffesump som
				annars skulle kasserats har blivit skönhetsprodukter sedan 2021. I Malmö återvinns
				kaffesump, havre och olja till skönhetsindustrin. -->
			<a
				href="https://www.aftonbladet.se/skonhet/a/0V8bbB/kaffesump-atervinns-till-skonhetsprodukt"
				target="_blank"
				class="btn">TILL ARTIKELN →</a
			>
		</div>
	</section>
</section>

<div class="shop-intro">
	<h2>Från naturen till ditt hem</h2>
	<p>
		Upptäck hur små förändringar kan göra stor skillnad i din vardag. På vår sida hittar du
		inspirerande artiklar och produkter som hjälper dig leva mer hållbart och medvetet. Starta dagen
		med en kopp nymalda kaffebönor från ekologiska gårdar eller skapa ett lugnare och grönare hem
		med våra utvalda växter. Låt dig inspireras till en mer medveten, grön livsstil.
	</p>
	<h4>Utforska vad vår sida har att erbjuda just dig</h4>
</div>

<HomeGrid items={data.pages} />

<style>
	/* Category-section */
	.cards {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 1rem;
	}

	.card {
		position: relative;
		text-align: center;
	}

	.card-img {
		width: 100%;
		object-fit: cover;
		border-radius: 1rem;
		max-height: 320px;
	}

	.card-overlay {
		position: absolute;
		top: 0;
	}

	.card-text {
		display: inline-block;
		text-align: center;
		color: white;
		line-height: 1.2;
		margin: 0.5rem 0;
		padding: 0.5rem;
	}

	.black-text {
		color: rgb(36, 20, 2);
		font-weight: 400;
		font-size: 1.05rem;
	}

	.btn {
		display: inline-block;
		border-radius: 2rem;
		padding: 0.5rem;
		text-decoration: none;
		background: #6e4e36;
		color: white;
		font-size: 0.8rem;
	}

	.btn:hover {
		background: rgba(51, 20, 10, 0.8);
	}

	.shop-intro {
		text-align: center;
	}

	/* Resposive Design */
	@media (max-width: 800px) {
		.cards {
			grid-template-columns: repeat(1, 2fr);
		}
	}
</style>
