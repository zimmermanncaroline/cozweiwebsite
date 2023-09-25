<script>
    export let countries;
    countries = [
        {
            id: "1",
            counName: "China",
            worldwide: "29,7",
            emission: "11.256",
            
        },
        {
            id: "2",
            counName: "USA",
            worldwide: "13,9",
            emission: "5.275"

        },
        {
            id: "3",
            counName: "Indien",
            worldwide: "6,9",
            emission: "2.622"
        },
        {
            id: "4",
            counName: "Russland",
            worldwide: "4,6",
            emission: "1.748"

        },
        {
            id: "5",
            counName: "Japan",
            worldwide: "3,2",
            emission: "1.199"
        },
        {
            id: "6",
            counName: "Deutschland",
            worldwide: "2,0",
            emission: "753"
        },
        {
            id: "7",
            counName: "Iran",
            worldwide: "1,9",
            emission: "728"
        },
        {
            id: "8",
            counName: "Südkorea",
            worldwide: "1,8",
            emission: "1,8"
        }
    ]
    
</script>

<h5>Länder</h5>

<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">CO2-Emission in Mio. t</th>
        <th scope="col">globaler Anteil in %</th>
      </tr>
    </thead>
    <tbody>
        {#each countries as country(country.id)}
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

<style>
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
</style>
