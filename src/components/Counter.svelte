<script>
    export let inferior = 0;
    export let superior = 9;
    let counter = 0;

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

<p>Contador entre {inferior} y {superior}.</p>
<button on:click={reduce} disabled={isReduceDisable}>-</button>
    {counter}
<button on:click={add} disabled={isAddDisable}>+</button>
<div>
    {messageIsLessThan1}
    {messageIsGreatherThan9}
</div>
<hr>
