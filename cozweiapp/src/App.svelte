<script>
//Import aller benötigten Komponenten
	import Intro from "./Intro.svelte";
	import Menue from "./Menue.svelte";
	import Nav from "./Nav.svelte";
	import Footer from "./Footer.svelte";
	import Filter from "./Filter.svelte";
</script>

<!-- Beginn des Markup-Bereichs -->
<main>
<!-- Einfügen der Komponentennamen an die gewünschte Position in Markups -->
<!-- Vergabe von ID´s für Sprungmarken -->
	<Nav />
	<br>
	<Menue />
	<br>
	<Intro />
	<br>
	<br>
	<Filter id="filter"/>
	<br>
	<br>
	<Footer id="footer" />
</main>
<!-- Ende Markup-Bereich -->

<style>
/* Styling des alle Elemente umgebenden main-Bereichs */
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