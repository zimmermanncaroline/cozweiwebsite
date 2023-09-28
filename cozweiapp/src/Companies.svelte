<script>
    import { writable } from "svelte/store";
    const Companies = writable(0);
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

<h5>Unternehmen</h5>
<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">globaler Anteil in % 
            <ul class="buttons">
                <li>
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

<style>
    ul.buttons { 
        float: right;
        list-style: none;
        padding: 0;
        margin: 0;
    }

    @media only screen and (max-width: 700px) {
        table thead tr th:nth-child(2) {
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
</style>
