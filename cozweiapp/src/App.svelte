<script>
	import Intro from "./Intro.svelte";
	import Menue from "./Menue.svelte";
	import Nav from "./Nav.svelte";
	import Footer from "./Footer.svelte";
    import Companies from "./Companies.svelte";
    import Countries from "./Countries.svelte";
</script>

<main>
	<Nav />
	<br>
	<Menue />
	<br>
	<Intro />
	<br>
	<Companies />
	<br>
	<Countries />
	<br>
	<Footer />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 90%;
		margin: auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>