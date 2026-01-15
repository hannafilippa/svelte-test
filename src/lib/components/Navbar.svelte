<script>
	import logo from '$lib/images/logo.png';

	// Svelte Playgournd : Responsive Navbar with simple Dropdown for mobile resolutions & max-width
	let isMenuOpen = false;
	let isSubMenuOpen = false;

	function dropMenu() {
		isMenuOpen = !isMenuOpen;
	}

	function dropSubMenu() {
		isSubMenuOpen = !isSubMenuOpen;
	}
</script>

<nav class="navbar">
	<div class="top-navbar">
		<a class="nav-logo" href="/">
			<img src={logo} alt="Green & Grounded logo" />
		</a>

		<button class="dropdown" on:click={dropMenu}>
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"
				><!--!Font Awesome Free v7.1.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2026 Fonticons, Inc.--><path
					d="M0 96C0 78.3 14.3 64 32 64l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 128C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 288c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32L32 448c-17.7 0-32-14.3-32-32s14.3-32 32-32l384 0c17.7 0 32 14.3 32 32z"
				/></svg
			></button
		>
	</div>

	<div class="nav-links" class:isMenuOpen>
		<a href="/" on:click={() => (isMenuOpen = false)}>Hem</a>
		<a href="/about" on:click={() => (isMenuOpen = false)}>Om Oss</a>
		<a href="/inspiration" on:click={() => (isMenuOpen = false)}>Artiklar</a>

		<!-- Submenu -->
		<div class="submenu">
			<button class="submenu-title" on:click={dropSubMenu}>Rekommendationer</button>

			{#if isSubMenuOpen}
				<div class="submenu-links" class:isSubMenuOpen>
					<a
						href="/recommendations"
						on:click={() => {
							isSubMenuOpen = false;
							isMenuOpen = false;
						}}>Se alla rekommendationer</a
					>
					<a
						href="/recommendations/coffee"
						on:click={() => {
							isSubMenuOpen = false;
							isMenuOpen = false;
						}}>Kaffe</a
					>
					<a
						href="/recommendations/plant"
						on:click={() => {
							isSubMenuOpen = false;
							isMenuOpen = false;
						}}>Växter</a
					>
				</div>
			{/if}
		</div>
	</div>
</nav>

<style>
	.navbar {
		display: flex;
		align-items: center;
		position: relative;
		background: rgb(232, 225, 222);
		padding-right: 1rem;
	}

	.top-navbar {
		display: flex;
		padding: 1rem;
	}

	.nav-logo img {
		height: 40px;
	}

	.nav-links {
		display: flex;
		margin-left: auto;
		gap: 1rem;
	}

	a,
	.submenu-title {
		font-family:
			'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
		font-size: 1rem;
		text-decoration: none;
		color: #333;
	}

	a:hover,
	.submenu-title:hover {
		color: #2e7d32;
	}

	/* Dropdown Submenu */
	.submenu {
		display: flex;
		flex-direction: column;
		padding-top: 0.2rem;
	}

	.submenu-title {
		background: none;
		border: none;
		cursor: pointer;
		line-height: 1.1;
		padding: 0;
	}

	.submenu-links {
		display: flex;
		flex-direction: column;
		gap: 0.3rem;
		padding: 0.5rem;

		position: absolute;
		z-index: 1;

		background: rgb(232, 225, 222);
		box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
	}

	/* Dropdown Menu */
	.dropdown {
		margin-left: auto;
		display: none;
	}

	svg {
		width: 15px;
		padding: 0.5rem 1rem;
	}

	/* Resposive Design - Mobile */
	@media (max-width: 550px) {
		.nav-links {
			display: none;
			flex-direction: column;
			padding: 0.7rem;

			position: absolute;
			z-index: 1;
			top: 90%;
			right: 0;

			margin-right: 2rem;
			background: rgb(232, 225, 222);
			box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
		}

		.top-navbar {
			width: 100%;
		}

		/* Dropdown Menu */
		.dropdown {
			display: block;
		}

		.isMenuOpen {
			display: flex;
		}

		/* Dropdown Submenu */
		.isSubMenuOpen {
			display: flex;
		}
	}
</style>
