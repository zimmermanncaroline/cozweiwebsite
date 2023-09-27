<script>
    import {companies} from "./Companies.svelte";
    for(let i = 0; i <= companies.length(), i++) {
        let listComp = companies[i].compName;
    }

</script>

<div>

    <p>{companies}</p>


</div>

<style>


</style>