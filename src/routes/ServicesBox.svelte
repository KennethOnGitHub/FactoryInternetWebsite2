<script>
    import SevicesLeft from "./SevicesLeft.svelte";

</script>
<div>
    <SevicesLeft />
</div>

<style>
    div {
        display: grid;
        grid-template-columns: 1fr 1fr;
        width: 90%;
        height: 80%;
        border-radius: 1%; 
        /* ^^^^ fix this */
        background-color: rgba(255, 255, 255, 0.235);
        padding: 2em;
    }


</style>