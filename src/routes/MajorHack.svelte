<script>
    import { onMount } from 'svelte';

    export let companyData;

    let index = 0;

    $: company = companyData[index].name;
    $: lost = companyData[index].lost;
    $: victimCount = companyData[index].victims;
    $: src = companyData[index].imgSrc;

    let alt = 'error: img failed to load';

    function cycle() {
        index += 1;
        index = index % companyData.length;
    }

    onMount(() => {
        const interval = setInterval(cycle, 2000);

        return () => {
            clearInterval(interval);
        }

    })
</script>

<div>
    <p>Company: <span>{company}</span></p>
    <p>Lost: <span>{lost}</span></p>
    <p>Victims: <span>{victimCount}</span></p>
    <img {src} alt = {company + " image"}>
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        background-color: #00000060;
        width: 320px;
        border-radius: 5%;
        padding: 0.3em;
        font-size: 1.4em;
    }
    span {
        color: red;
    }
    img {
        width: 300px;
        height: 225px;
        align-self: center;
        border-radius: 5%;
        
    }
    

</style>
