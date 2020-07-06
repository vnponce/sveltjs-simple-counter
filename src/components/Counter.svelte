<script>
    // export - Values that are passed in as props
    export let inferior = 0;
    export let superior = 9;
    let counter = inferior;

    // the `$:` means 're-run whenever these values change'
    // It's like a Vuejs computed property
    $: isReduceDisable = counter <= inferior;
    $: messageIsLessThan1 = isReduceDisable ? `No puede ser menor a ${counter}` : '';
    $: isAddDisable = counter >= superior;
    $: messageIsGreatherThan9 = isAddDisable ? `No puede ser mayor a ${counter}` : '';


    function add() {
      counter += 1;
    }

    function reduce() {
      counter -= 1;
    }
</script>

<style>
    button {
        width: 70px;
        margin: 10px;
        cursor: pointer;
    }
    button:disabled {
         cursor: not-allowed;
     }
</style>

<p>Contador entre {inferior} y {superior}.</p>
<button on:click={reduce} disabled={isReduceDisable}>-</button>
    {counter}
<button on:click={add} disabled={isAddDisable}>+</button>

<div>
{#if messageIsLessThan1 || messageIsGreatherThan9 }
    {messageIsLessThan1}
    {messageIsGreatherThan9}
{:else}
    -
{/if}
</div>
<hr>
