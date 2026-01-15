<script>
	//tom
</script>

<footer>
	<div class="column">
		<h5>INFORMATION</h5>
		<a href="/">Shop Pay</a>
		<a href="/">Help center</a>
		<a href="/">For brands</a>
	</div>

	<div class="column">
		<h5>LEGAL</h5>
		<a href="/">Terms of Service</a>
		<a href="/">Privacy Policy</a>
		<a href="/">Manage Cookies</a>
	</div>

	<div class="column">
		<h5>CONTACT</h5>
		<p class="contact">Green & Grounded</p>
		<p class="contact">Greenery 1</p>
		<p class="contact">13 100 Greenland</p>
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
		gap: 1rem;

		background-color: rgba(61, 28, 13, 0.6);
		margin-top: 1rem;
		padding-bottom: 2rem;
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
		padding: 0 20px;
	}

	/* Responsive Design */
	@media (max-width: 800px) {
		footer {
			grid-template-columns: repeat(3, 1fr);
		}
	}

	@media (max-width: 550px) {
		footer {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
