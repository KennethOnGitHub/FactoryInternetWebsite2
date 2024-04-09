<script>
    import { onMount } from "svelte";

    const lostInYear = 9_500_000_000_000; //change this later

    const msInYear = 31_536_000_000;

    let now = new Date;
    const startOfYear = new Date(now.getFullYear(), 0, 1);

    $: timeSinceStartOfYear = now.getTime() - startOfYear.getTime();

    $: cost = (timeSinceStartOfYear/msInYear) * lostInYear;
    $: formattedCost = cost.toLocaleString('en-US', { maximumFractionDigits: 2, minimumFractionDigits: 2 });

    onMount(() => {
        const interval = setInterval(() => {
            now = new Date;
        }, 50) 
    })
</script>

<div>
    <h1>
        ${formattedCost}
    </h1>
    <h2>
        Lost to Cyber Attacks in 2024
    </h2>
</div>

<style>
    div {
        text-align: center;
        font-size: 1em;
    }
    h1 {
        font-size: 3.5em;
        color: red;
    }
    h2 {
        font-size:2em;
    }
</style>