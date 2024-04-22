<script>
    import { createEventDispatcher } from "svelte";
    import SlideCover from "./SlideCover.svelte";

    export let title = "NO TITLE!";
    export let src;
    export let text = "text fail!!!";

    let mode = 'active';

    const dispatch = createEventDispatcher();
</script>

<div class = {mode} on:mouseenter={() => {mode = 'inactive'}} on:mouseleave = {() => {mode = 'active'}}>
    <SlideCover {title} {src} {mode}/>
    <p class = {mode}> {text} </p>
</div>

<style>
    div {
        width: 300px;
        height: 300px;
        position: relative;
        border: 4px solid #086ad8;
        border-radius: 25px;
        padding: 10px;

        transition: background-color 0.3s;
    }

    p {
        position: absolute;
        top:10px;
        left:10px;
        width: 272px;
        /* ^^^^ setting width like this is bad, but time constraints forced my hand */
        color: rgb(255, 255, 255);
        text-shadow: 2px 2px #000000;
        z-index: 1;
    }

    p.active{
        /* background-color: #086ad8; */
        z-index: -1;
        opacity: 0;
    }

    p.inactive{
        z-index: 1;
        opacity: 100%;
    }

    div.inactive {
        background-color: #0869d869;
    }

</style>