<script>
    import MajorHack from "./MajorHack.svelte";

    import heartlandLogo from '$lib/assets/Heartland.jpg';
    import anthemLogo from '$lib/assets/anthem.webp'
    import playstationLogo from '$lib/assets/playstation.jpg'
    import homedepotLogo from '$lib/assets/homedepot.jpg'
    import exactisLogo from '$lib/assets/exactis.jpg'
    const hackData1 = [
        {name: 'Heartland Payment', lost: '$60 Million', victims: '~134 Million', imgSrc: heartlandLogo},
        {name: 'Anthem', lost: '$40 Million', victims: '78.8 Million', imgSrc: anthemLogo},
        {name: 'Playstation', lost: '$15 Million', victims: '77 Million', imgSrc: playstationLogo},
        {name: 'Home Depot', lost: '$17.5 Million', victims: '50 million', imgSrc: homedepotLogo},
        {name: 'Exactis', lost: 'Cost undetermined', victims: '340 Million', imgSrc: exactisLogo},
    ]

    import targetLogo from '$lib/assets/Target.jpg';
    import equifaxLogo from '$lib/assets/Equifax.webp'
    import yahooLogo from '$lib/assets/Yahoo.webp'
    import mariottLogo from '$lib/assets/Marriot.jpg'
    import capitalOneLogo from '$lib/assets/capitalOne.jpg'
    const hackData2 = [
        {name: 'Target', lost: '$200 Million', victims: '70 Million', imgSrc: targetLogo},
        {name: 'Equifax', lost: '$575 Million', victims: '147 Million', imgSrc: equifaxLogo},
        {name: 'Yahoo', lost: '$117 Million', victims: '3 Billion', imgSrc: yahooLogo},
        {name: 'Marriot', lost: '$18.4 Million', victims: '500 Million', imgSrc: mariottLogo},
        {name: 'Capital One', lost: '$190 Million', victims: '100 Million', imgSrc: capitalOneLogo},
    ]

    import uberLogo from '$lib/assets/uber.webp';
    // import equifaxLogo from '$lib/assets/Equifax.webp'
    // import yahooLogo from '$lib/assets/Yahoo.webp'
    // import mariottLogo from '$lib/assets/Marriot.jpg'
    // import capitalOneLogo from '$lib/assets/capitalOne.jpg'
    const hackData3 = [
        {name: 'Uber', lost: '$148 Million', victims: '57 Million', imgSrc: uberLogo},
        {name: 'Equifax', lost: '$575 Million', victims: '147 Million', imgSrc: equifaxLogo},
        {name: 'Yahoo', lost: '$117 Million', victims: '3 Billion', imgSrc: yahooLogo},
        {name: 'Marriot', lost: '$18.4 Million', victims: '500 Million', imgSrc: mariottLogo},
        {name: 'Capital One', lost: '$190 Million', victims: '100 Million', imgSrc: capitalOneLogo},
    ]

</script>


<div>
    <MajorHack companyData = {hackData1}/>
    <MajorHack companyData = {hackData2}/>
    <MajorHack companyData = {hackData3}/>
</div>
<h3>
    Don't be the next one
</h3>

<style>
    div {
        display: flex;
        justify-content: space-evenly;
    }
    h3 {
        text-align: center;
    }
    
</style>