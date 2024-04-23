<script>
    import { onMount } from 'svelte';
    import targetLogo from '$lib/assets/Target.jpg';
    import equifaxLogo from '$lib/assets/Equifax.webp'
    import yahooLogo from '$lib/assets/Yahoo.webp'
    import mariottLogo from '$lib/assets/Marriot.jpg'
    import capitalOneLogo from '$lib/assets/capitalOne.jpg'

    const companyData = [
        {name: 'Target', lost: '$200 Million', victims: '70 Million', imgSrc: targetLogo},
        {name: 'Equifax', lost: '$575 Million', victims: '147 Million', imgSrc: equifaxLogo},
        {name: 'Yahoo', lost: '$117 Million', victims: '3 Billion', imgSrc: yahooLogo},
        {name: 'Marriot', lost: '$18.4 Million', victims: '500 Million', imgSrc: mariottLogo},
        {name: 'Capital One', lost: '$190 Million', victims: '100 Million', imgSrc: capitalOneLogo},
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
