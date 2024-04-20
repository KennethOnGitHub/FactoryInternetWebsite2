<script>
    import { onMount } from 'svelte';
    const companyData = [
        {name: 'Target', lost: '$200 Million', victims: '70 Million', imgSrc: 'src/lib/assets/Target.jpg'},
        {name: 'Equifax', lost: '$575 Million', victims: '147 Million', imgSrc: 'src/lib/assets/Equifax.webp'},
        {name: 'Yahoo', lost: '$117 Million', victims: '3 Billion', imgSrc: 'src/lib/assets/Yahoo.webp'},
        {name: 'Marriot', lost: '$18.4 Million', victims: '500 Million', imgSrc: 'src/lib/assets/Marriot.jpg'},
        {name: 'Capital One', lost: '$190 Million', victims: '100 Million', imgSrc: 'src/lib/assets/CapitalOne.jpg'},
    ]

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
