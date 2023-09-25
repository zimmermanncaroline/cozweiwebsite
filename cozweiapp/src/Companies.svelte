<script>
    export const companies = [
        {
            id: "1",
            compName: "China (Coal)",
            emission: "14,32"
        },
        {
            id: "2",
            compName: "Saudi Arabian Oil Company (Aramco)",
            emission: "4,5"

        },
        {
            id: "3",
            compName: "Gazprom OAO",
            emission: "3,91"
        },
        {
            id: "4",
            compName: "National Iranian Oil Co",
            emission: "2,28"

        },
        {
            id: "5",
            compName: "ExxonMobil Corp",
            emission: "1,98"
        },
        {
            id: "6",
            compName: "Coal India",
            emission: "1,87"
        },
        {
            id: "7",
            compName: "Petroleos Mexicanos (Pemex)",
            emission: "1,87"
        }
    ]
 
</script>

<h5>Unternehmen</h5>

<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">globaler Anteil in %</th>
      </tr>
    </thead>
    <tbody>
        {#each companies as company(company.id)}
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
    .table {
        max-width: 600px;
        margin: auto;
    }

    .table {
        background-color:  #80BD9E;
    }

    thead th:nth-child(1) {
        text-align: left;
    }
    tbody td:nth-child(odd) {
        text-align: left;
    }

    #quelle {
        font-size: small;
        text-align: left;
        padding-left: 5%;
    }
</style>
