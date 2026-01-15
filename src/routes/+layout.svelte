<script>
	import '../styles/global.css';

	import logo from '$lib/images/logo.png';
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={logo} />
</svelte:head>

<Navbar />

<div class="app">
	{@render children?.()}
</div>

<Footer />
