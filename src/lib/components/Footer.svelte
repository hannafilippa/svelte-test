<script>
	//
</script>

<footer>
	<div class="column">
		<h5>INFORMATION</h5>
		<a href="/">Annonsinfo</a>
		<a href="/">Hjälpcenter</a>
		<a href="/">Tillgänglighet</a>
	</div>

	<div class="column">
		<h5>ALLMÄNNA VILLKOR</h5>
		<a href="/">Användarvillkor</a>
		<a href="/">Integritetspolicy</a>
		<a href="/">Hantera Cookies</a>
	</div>

	<div class="column">
		<h5>KONTAKT</h5>
		<p class="contact">Jordnära Välmående</p>
		<p class="contact">Landet 1</p>
		<p class="contact">13 100 Jorden</p>
	</div>

	<div class="column">
		<h5>SOCIAL</h5>
		<a href="/">Facebook</a>
		<a href="/">Instagram</a>
	</div>
</footer>

<style>
	footer {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		background-color: rgba(61, 28, 13, 0.6);
		margin-top: 1rem;
		padding-bottom: 2rem;
		justify-items: center;
	}

	footer h5 {
		font-size: 1rem;
		color: beige;
	}

	footer a,
	p {
		font-size: 1rem;
		color: white;
		text-decoration: none;
		margin-block: 0;
	}

	footer a:hover {
		color: beige;
	}

	.column {
		display: flex;
		flex-direction: column;
		padding: 0 10px;
	}

	/* Responsive Design */
	@media (max-width: 800px) {
		footer {
			grid-template-columns: repeat(3, 1fr);
			justify-items: normal;
			padding-left: 0.5rem;
		}
	}

	@media (max-width: 550px) {
		footer {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
