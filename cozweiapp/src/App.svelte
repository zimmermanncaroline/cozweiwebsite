<script>
	import Intro from "./Intro.svelte";
	import Menue from "./Menue.svelte";
	import Nav from "./Nav.svelte";
    import ValuesCountries from "./ValuesCountries.svelte";
	import Footer from "./Footer.svelte";
    import ValuesCompanies from "./ValuesCompanies.svelte";
    import Companies from "./Companies.svelte";
</script>

<main>
	<Nav />
	<br>
	<Menue />
	<br>
	<Intro />
	<br>
	<br>
	<ValuesCountries />
	<br>
	<ValuesCompanies />
	<br>
	<Companies />
	<br>

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