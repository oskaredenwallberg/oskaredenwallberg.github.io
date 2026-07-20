<script lang="ts">
	import 'katex/dist/katex.min.css';
	import "../app.css";

	import Navbar from "$lib/components/Navbar.svelte";
	import Footer from "$lib/components/Footer.svelte";
	
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/favicon.svg" />
</svelte:head>

<div class="page">
	<Navbar />

	<main>
		{@render children()}
	</main>

	<Footer />
</div>


<style>
	.page {
		max-width: 1100px;
		margin: 0 auto;
		padding: 0 clamp(1rem, 8vw, 10rem);
	}
</style>