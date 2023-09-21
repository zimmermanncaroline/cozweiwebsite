<script>
    let test = "Das ist doch schön";
    const increase  = () => {
      test = "Das war doch schön";
    }
    export let name, vorname;
</script>
<p>{name}</p>
<p>{vorname}</p>
<label for="name">Gib mal deinen namen ein:
<input type="text" bind:value={name}>
</label>
<button on:click={increase}>klick mal</button>
<button on:click={changeName}>Name ändern</button>
<div class="row">
    <aside class="col-md-2">
        <h3>{test}</h3>
        <form action="/filter">
            <label>
                <input type="checkbox" value="all" id="all">Alle
            </label>
            <label>
                <input type="checkbox" name="filter" value="companies">Unternehmen
            </label>
            <label>
                <input type="checkbox" name="filter" value="countries">Länder
            </label>
        </form>
    </aside>
</div>

<h3>Länder</h3>
<table class="table">
    <thead>
      <tr>
        <th scope="col">Name</th>
        <th scope="col">CO2-Emission in Mio. t</th>
        <th scope="col">globaler Anteil in %</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>USA</td>
        <td>5.275</td>
        <td>13,9</td>
      </tr>
      <tr>
        <td>Indien</td>
        <td>2.622</td>
        <td>6,9</td>
      </tr>
      <tr>
        <td>Russland</td>
        <td>1.748</td>
        <td>4,6</td>
      </tr>
      <tr>
        <td>Japan</td>
        <td>1.199</td>
        <td>3,2</td>
      </tr>
      <tr>
        <td>Deutschland</td>
        <td>753</td>
        <td>2,0</td>
      </tr>
      <tr>
        <td>Iran</td>
        <td>728</td>
        <td>1,9</td>
      </tr>
      <tr>
        <td>Südkorea</td>
        <td>695</td>
        <td>18</td>
      </tr>
      <tr>
      <td id="quelle" colspan="4"><a href="#">Quelle: https://www.co2online.de/klima-schuetzen/klimawandel/co2-ausstoss-der-laender/</a></td>
    </tr>
    </tbody>
  </table>

  <style>
    table {
      max-width: 750px;
      margin: auto;
    }

    #quelle {
        font-size: small;
        text-align: left;
        padding-left: 5%;
    }
</style>
