<script>
	import Header from './components/Header/Header.svelte';
	import './main.sass'
	import Footer from "./components/Footer/Footer.svelte";
</script>

<svelte:head>
	<link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
</svelte:head>

<div class="app">
	<div class="paper_bg"></div>
	<Header />

	<main>
		<slot />
	</main>

	<Footer />
</div>
