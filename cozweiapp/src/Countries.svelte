<script>
// Import von benötigten Komponenten
/* zum Wiederverwenden und Filtern der Daten muss die Funktion writeable aus der 
    Svelte-Bibliothek importiert werden */
    import { writable } from 'svelte/store';
	const Countries = writable(0);
// Daten Speichern in einem Array
    $Countries = [
        {
            "counName": "China",
            "worldwide": 29.7,
            "emission": 11.256,
        },
        {
            "counName": "USA",
            "worldwide": 13.9,
            "emission": 5.275,
        },
        {
            "counName": "Indien",
            "worldwide": 6.9,
            "emission": 2.622,
        },
        {
            "counName": "Russland",
            "worldwide": 4.6,
            "emission": 1.748,
        },
        {
            "counName": "Japan",
            "worldwide": 3.2,
            "emission": 1.199,
        },
        {
            "counName": "Deutschland",
            "worldwide": 2.0,
            "emission": 753,
        },
        {
            "counName": "Iran",
            "worldwide": 1.9,
            "emission": 728,
        }
    ];
// Sortierfunktion, bei der die einzelnen Emissionswerte vergleichen werden
    function sortCountrie(multiplier) {
		$Countries.sort((a,b) => { 
			if (a.worldwide > b.worldwide) {
				return 1 * multiplier;
			}
			
			if (a.worldwide < b.worldwide) {
				return -1 * multiplier;
			} 
			return 0;
		})
		$Countries = $Countries;
	}
</script>

<!-- Beginn des Markup-Bereichs -->
<h4>Länder</h4>
<!-- Beginn Tabelle -->
<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">CO2-Emission in Mio. t</th>
        <th scope="col">globaler Anteil in % 
<!-- Anlegen der Sortier-Buttons in einer Liste -->
            <ul class="buttons">
                <li>
<!-- Aufrufen der Soriterfunktion aufsteigend und absteigend innerhalb der Button-->
                    <button id="up" on:click={() => {sortCountrie(1)}}>&#9650;</button>
                </li>
                <li>
                    <button id="up" on:click={() => {sortCountrie(-1)}}>&#9660;</button>
                </li>
            </ul>
        </th>
      </tr>
    </thead>
    <tbody>
<!-- Durchlaufen des Arrays und Anlegen der Daten in die Tabelle -->
        {#each $Countries as country}
        <tr>
            <td>{country.counName}</td>
            <td>{country.emission}</td>
            <td>{country.worldwide}</td>
        </tr>
        {/each}
        <tr>
            <td id="quelle" colspan="4"><a href="https://www.co2online.de/klima-schuetzen/klimawandel/co2-ausstoss-der-laender/" target="_blank">Quelle: https://www.co2online.de/klima-schuetzen/klimawandel/co2-ausstoss-der-laender/</a></td>
        </tr>
    </tbody>
</table>
<!-- Ende Markup-Bereich -->

<style>
    ul.buttons { 
        float: right;
        list-style: none;
        padding: 0;
        margin: 0;
    }

    ul.buttons li {
        display: inline;
    }

    button {
        background-color: white;
        width: 2em;
        height: 2em;
        padding: 0px;
        text-align: center;
        vertical-align: middle;
        margin: 0px;
    }

    table {
        max-width: 600px;
        margin: auto;
    }

    thead th:nth-child(1) {
        text-align: left;
    }

    tbody td:nth-child(1) {
        text-align: left;
    }

    #quelle {
        font-size: small;
        text-align: left;
        padding-left: 5%;
    }

/* Mediaqueries für kleiner Bildschirme unter 700px */
    @media only screen and (max-width: 700px) {
        table thead tr th:nth-child(3) {
            position: relative;
        }

        button {
            width: 1.5em;
            height: 1.5em;
        }

        ul.buttons {
            position: absolute;
            right: -20px;
            top: 10px;
            width: 20px;
        }

        ul.buttons li {
            display: block;
        }
    }

</style>
