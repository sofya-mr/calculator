<script>
    import {createEventDispatcher} from 'svelte';
    const dispatch=createEventDispatcher();


    export let num;
    export let action;
    export let span;
    export let highlighted;

    function addNumber () {
        dispatch('printNumber', (action || num))
    };
</script>



<button class:span={span} class:action={typeof num != "number"} class:highlighted={highlighted} on:click={addNumber}>{num}</button>



<style>
    button {
        width: 80px;
        margin-bottom: 0;
    }

    button.span {
        width: 100%;
    }
    
    button.action {
        background-color: #e5e7e8;
    }

    button.highlighted {
        background-color: #95f8a5;
    }
</style>
