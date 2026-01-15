<script>
	import SectionIntro from '$lib/components/SectionIntro.svelte';
	import habits from '$lib/images/habits.jpg';
	import todos from '$lib/images/todos.jpg';

	let { data } = $props();
</script>

<SectionIntro
	image={habits}
	imageAlt="dagstidning"
	title="Dina vanor - ett sätt att strukturera din vardag"
	text="Här kan du spara idéer, skapa personliga listor och följa dina hållbara mål direkt på hemsidan. Oavsett om du vill planera framtida inköp, samla inspiration för en grönare vardag eller hålla koll på små förändringar du vill genomföra, finns allt samlat på ett och samma ställe. Vi vill stötta dig i att ta steg mot en mer hållbar livsstil genom att vara en plats att återvända till - för struktur, motivation och små val som tillsammans gör stor skillnad över tid."
/>

<div class="section" id="section">
	<div class="todos-section">
		<h1>Din första lista</h1>

		<form method="POST" action="?/create#section" class="todo-form">
			<label>
				<input
					name="description"
					placeholder="Vad vill du lägga till i listan?"
					autocomplete="off"
					required
				/>
			</label>
		</form>

		<ul class="todos">
			{#each data.todos as todo (todo.id)}
				<li class="todo-item">
					<form method="POST" action="?/delete#section">
						<input type="hidden" name="id" value={todo.id} />
						<span>{todo.description}</span>
						<button aria-label="Ta bort todo"></button>
					</form>
				</li>
			{/each}
		</ul>
	</div>
	<img src={todos} alt="penna och dagbok" />
</div>

<style>
	h1,
	label {
		color: green;
	}

	.section {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 1rem;
	}

	.todos-section {
		margin-left: 0.5rem;
		padding: 0 0.5rem;
		border-radius: 1rem;
		background-color: rgba(194, 192, 190, 0.195);
	}

	.todo-form input {
		width: 93%;
		margin-top: 0.5rem;
		padding: 0.75rem;
		border-radius: 0.5rem;
		border: 1px solid #ccc;
	}

	.todos {
		list-style: none;
		margin-top: 1rem;
		padding: 0;
	}

	.todo-item {
		width: 93%;
		padding: 0.75rem;
		margin-bottom: 0.5rem;
		background: #fff;
		box-shadow: 2px 2px rgba(0, 0, 0, 0.05);
		border-radius: 0.5rem;
	}

	.todo-item form {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	button {
		border: none;
		background: url(./remove.svg) no-repeat center;
		cursor: pointer;
		background-size: 1rem;
		height: 1rem;
		opacity: 0.5;
	}

	button:hover {
		opacity: 1;
	}

	img {
		width: 100%;
		object-fit: cover;
		border-radius: 1rem;
	}

	/* Resposive Design */
	@media (max-width: 800px) {
		.section {
			grid-template-columns: repeat(1, 1fr);
			margin: 0 auto;
			padding: 0.5rem;
		}

		.todos-section {
			margin-left: 0;
		}
	}

	@media (max-width: 550px) {
		img {
			margin: 0;
		}
	}
</style>
