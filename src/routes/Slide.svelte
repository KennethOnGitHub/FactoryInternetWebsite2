<script>
    import SlideCover from "./SlideCover.svelte";

    export let title = "NO TITLE!";
    export let src;
    export let text = "text fail!!!";
</script>

<div>
    <SlideCover {title} {src}/>
    <p>{text}</p>
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
</style>