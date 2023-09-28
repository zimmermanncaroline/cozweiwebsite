<script>
// Import von benötigten Komponenten
/* zum Wiederverwenden und Filtern der Daten muss die Funktion writeable aus der 
    Svelte-Bibliothek importiert werden */
    import { writable } from "svelte/store";
    const Companies = writable(0);
// Daten Speichern in einem Array
    $Companies = [
        {
            compName: "China (Coal)",
            emission: 14.32,
        },
        {
            compName: "Saudi Arabian Oil Company (Aramco)",
            emission: 4.5,
        },
        {
            compName: "Gazprom OAO",
            emission: 3.91,
        },
        {
            compName: "National Iranian Oil Co",
            emission: 2.28,
        },
        {
            compName: "ExxonMobil Corp",
            emission: 1.98,
        },
        {
            compName: "Coal India",
            emission: 1.87,
        },
        {
            compName: "Petroleos Mexicanos (Pemex)",
            emission: 1.87,
        }
    ];
// Sortierfunktion, bei der die einzelnen Emissionswerte vergleichen werden
    function sortCompanies(multiplier) {
        $Companies.sort((a,b) => {
            if (a.emission > b.emission) {
                return 1 * multiplier;
            }
            if (a.emission < b.emission) {
                return -1 * multiplier;
            }
            return 0;
        })
        $Companies = $Companies;
    }
</script>

<!-- Beginn des Markup-Bereichs -->
<h4>Unternehmen</h4>
<!-- Beginn Tabelle -->
<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">globaler Anteil in % 
<!-- Anlegen der Sortier-Buttons in einer Liste -->
            <ul class="buttons">
                <li>
<!-- Aufrufen der Soriterfunktion aufsteigend und absteigend innerhalb der Button-->
                    <button id="up" on:click={() => {sortCompanies(1)}}>&#9650;</button>
                </li>
                <li>
                    <button id="up" on:click={() => {sortCompanies(-1)}}>&#9660;</button>
                </li>
            </ul>
        </th>
      </tr>
    </thead>
    <tbody>
<!-- Durchlaufen des Arrays und Anlegen der Daten in die Tabelle -->
        {#each $Companies as company}
        <tr>
            <td>{company.compName}</td>
            <td>{company.emission}</td>
        </tr>
        {/each}
        <tr>
            <td id="quelle" colspan="4"><a href="https://kontrast.at/corona-klima/" target="_blank">Quelle: https://kontrast.at/corona-klima/</a></td>
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

    .table {
        max-width: 600px;
        margin: auto;
        background-color:  #80BD9E;
    }

    thead th:nth-child(1) {
        text-align: left;
    }

    tbody td:nth-child(odd) {
        text-align: left;
        white-space: nowrap;
    }

    #quelle {
        font-size: small;
        text-align: left;
        padding-left: 5%;
    }
/* Mediaqueries für kleiner Bildschirme unter 700px */
    @media only screen and (max-width: 700px) {
        table thead tr th:nth-child(2) {
            position: relative;
        }         
    }
</style>
