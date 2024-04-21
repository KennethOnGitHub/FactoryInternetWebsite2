<script>
    import Slide from './Slide.svelte';

    import malwareImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import socialEngineeringImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import denialOfServiceImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import vulnerabilitiesImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import Carousel from './Carousel.svelte';

    const Topics = [
        {slide: {title: "Malware", src: malwareImg, text:'Lorem isupm GANNNNNG 1 The industrial revolution and its consequences were realllll interesting guys'}, 
        content: `Mal - The Crimean War was a very important war of the 19th century. It saw France under Napoleon III stand up to Russia's claims over churches in the Ottoman empire. 
        From this it grew into a larger conflict, where Britain, France, Sardinia-Piedmont and the Ottomans faced off against Russia. The coalition of the Western powers came out victorious, but what if this changed?
        If Russia won the war, would they have taken the entire Balkans, paving the way for global domination?`},

        {slide: {title: "Social Engineering", src: socialEngineeringImg, text:'Lorem isupm GANNNNNG 2'},
        content: `Soc - The Crimean War was a very important war of the 19th century. It saw France under Napoleon III stand up to Russia's claims over churches in the Ottoman empire. 
        From this it grew into a larger conflict, where Britain, France, Sardinia-Piedmont and the Ottomans faced off against Russia. The coalition of the Western powers came out victorious, but what if this changed?
        If Russia won the war, would they have taken the entire Balkans, paving the way for global domination?`},

        {slide: {title: "Denial-Of-Service", src: denialOfServiceImg, text:'Lorem isupm GANNNNNG 3'}, 
        content: `The Crimean War was a very important war of the 19th century. It saw France under Napoleon III stand up to Russia's claims over churches in the Ottoman empire. 
        From this it grew into a larger conflict, where Britain, France, Sardinia-Piedmont and the Ottomans faced off against Russia. The coalition of the Western powers came out victorious, but what if this changed?
        If Russia won the war, would they have taken the entire Balkans, paving the way for global domination?`},

        {slide: {title: "Vulnerabilites", src: vulnerabilitiesImg, text:'Lorem isupm GANNNNNG 4'}, 
        content: `The Crimean War was a very important war of the 19th century. It saw France under Napoleon III stand up to Russia's claims over churches in the Ottoman empire. 
        From this it grew into a larger conflict, where Britain, France, Sardinia-Piedmont and the Ottomans faced off against Russia. The coalition of the Western powers came out victorious, but what if this changed?
        If Russia won the war, would they have taken the entire Balkans, paving the way for global domination?`},        
    ]


    let navigating = true;
    let contentIndex = 0;

    console.log("test");

</script>

<div class = "threats-page">
    <h1 class = "header" id="2">Meet some threats</h1>

    <div class = {(navigating? "nav-mode" : "") + " container"}>
        <nav>
            {#each Topics as {slide}, i}
            <button on:click={() => {navigating = false; contentIndex = i}}>
                <Slide {...slide}/>
            </button>       
        {/each}
        </nav>
    
        <div class = 'wrapper'>
            <div class = 'content'>
                <h2>{Topics[contentIndex].slide.title}</h2>
                <Carousel />
                <button on:click = {() => navigating = true}>Back</button>
            </div>
        </div>
    
    </div>
</div>

<style>
    .threats-page {
        display: flex;
        flex-direction: column;
        background-color: #F8F8F8;
        height: 800px;
        padding: 30px 0px;
        width: 100vw;
    }

    h1 {
        color: black;
        padding-left: 56px;
    }

    .container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        width: 200vw;
        height: 100%;
        /* not sure why height 100% works tbh, no time to figure it out tho */

        position: relative;
        left: -100%;

        transition: position, 1s;
    }

    nav {
        flex-grow: 1;

        display: flex;
        align-items: center;
        justify-content: center;
    }

    button {
        background: transparent;
        border: none;
        cursor: pointer;
    }

    .wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .content {
        background-image: linear-gradient(to bottom, #086AD8, #043872);
        width: 80%;
        height: 80%;
        border-radius: 10px;
        padding: 1em;
    }

    h2 {
        text-decoration: underline;
    }

    .nav-mode {
        left:0;
    }


</style>