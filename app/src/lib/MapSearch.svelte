<script lang="ts">
    import {createEventDispatcher} from "svelte";

    enum Events { Search = 'search'}

    let dispatch = createEventDispatcher()

    let text: string
</script>

<input type="text" placeholder="🔍 Search UVIC..." bind:value={text} on:change={() => {
    if (text.length > 2) {
        dispatch(Events.Search, {text})
    }
}} on:dblclick={(event) => {
    event.stopPropagation();
}}>
  
  
<style>
    input{
        margin-left: 2rem;
        padding-left: 1rem;
        border-radius: .5rem;
        height: 1.9rem;
        width: 20rem;  
        font-size: 0.9rem;
        border: 2.6px solid rgb(0, 0, 0);
        box-shadow: 0 4px 3px rgba(126, 126, 126, 0.2);
    }

    input:active{
        border: 2.6px solid rgb(70, 139, 243);
    }

</style>

