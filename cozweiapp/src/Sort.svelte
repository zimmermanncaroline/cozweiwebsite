<script>
    import {companies} from "./Companies.svelte";
    const listComp = [];
</script>

<div>
    {#each companies as comp(compName)}
    <p>{listComp.push()}</p>
    {/each}

</div>

<style>


</style>