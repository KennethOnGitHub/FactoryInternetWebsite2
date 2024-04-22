<script>
    export let title = "NO TITLE!";
    export let src;
    export let mode = 'active';
</script>

<div class = {mode}>
    <img {src} alt = 'PLACEHOLDER! REPLACE LATER!'>
    <h3>{title}</h3>
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        height: 100%;
        transition: filter 0.1s;
    }

    img {
        height: 80%;
    }

    .active {
        z-index: 1;
        filter: blur(0);
    }

    .inactive {
        filter: blur(5px);
        z-index: -1;
    }

    h3 {
        color: black;
    }
</style>
