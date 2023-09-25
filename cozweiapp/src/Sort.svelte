<script>
  import {companies} from "./Companies.svelte";

</script>

<div>
    {#each companies as comp(comp.id)}
    <p>{comp.compName}</p>
    {/each}

</div>

<style>


</style>