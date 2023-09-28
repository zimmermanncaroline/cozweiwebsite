<script>
// Import von benötigten Komponenten
    import Countries from "./Countries.svelte";
    import Companies from "./Companies.svelte";
// Anlegen von boolschen Variablen
    let showCompData = true;
    let showCounData = true;
// Funktionen zum Ein- und Ausblenden von Markup-Inhalten   
    const toggleComp = () => {
        showCompData = !showCompData;
    }

    const toggleCoun = () => {
        showCounData = !showCounData;
    }
</script>

<!-- Beginn des Markup-Bereichs -->
<div>
<!-- Buttons mit Funktion zum Ein- und Ausblenden von Markup-Inhalten-->
    <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">
        <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off" checked on:click={toggleCoun}>
        <label class="btn btn-outline-primary" for="btncheck1">Länder</label>
      
        <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off" checked on:click={toggleComp}>
        <label class="btn btn-outline-primary" for="btncheck3">Unternehmen</label>
    </div>
<!-- Bedingte Abfrage zum Anzeigen der Daten -->
    <div class="table">
        {#if showCompData}
            <Companies />
        {/if}
    </div>
    <div class="table">
    {#if showCounData}
        <Countries />
    {/if}
    </div>
</div>
<!-- Ende des Markup-Bereichs -->

<style>
    .table {
        margin-top: 3em;
    }
</style>