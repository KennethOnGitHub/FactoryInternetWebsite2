<script>
    export let title = "NO TITLE!";
    export let src;

</script>

<div>
    <img {src} alt = 'PLACEHOLDER! REPLACE LATER!'>
    <h3>{title}</h3>
</div>

<style>
    div {
        text-align: center;
        width: 100%;
        height: 100%;
    }

    div:hover {
        filter:blur(5px)
    }

    h3 {
        color: black;
    }
</style>
