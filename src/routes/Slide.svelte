<script>
    import SlideCover from "./SlideCover.svelte";

    export let title = "NO TITLE!";
    export let src;
    export let text = "text fail!!!";

    let mode = 'active';
</script>

<div on:mouseenter={() => {mode = 'inactive'}} on:mouseleave = {() => {mode = 'active'}}>
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
        margin: 1%;
    }

    p {
        position: absolute;
        top:10px;
        left:10px;
        color: black;
        z-index: 1;
    }

    p.active{
        z-index: -1;
        opacity: 0;
    }

    p.inactive{
        z-index: 1;
        opacity: 100%;
    }

</style>