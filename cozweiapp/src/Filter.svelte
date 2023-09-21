<script>
    import Countries from "./Countries.svelte";
    import Companies from "./Companies.svelte";

    let showCompData = true;
    let showCounData = true;

    const toggleAll = () => {
        showCompData = true;
        showCounData = true;
    }

    const toggleComp = () => {
        showCompData = !showCompData;
    }

    const toggleCoun = () => {
        showCounData = !showCounData;
    }
</script>

<div>
    <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">
        <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off" checked on:click={toggleCoun}>
        <label class="btn btn-outline-primary" for="btncheck1">Länder</label>
      
        <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off" checked on:click={toggleComp}>
        <label class="btn btn-outline-primary" for="btncheck3">Unternehmen</label>
      </div>
      <br><br>
    {#if showCompData}
        <Companies />
    {/if}
    <br>
    {#if showCounData}
        <Countries />
    {/if}
</div>

<style>


</style>