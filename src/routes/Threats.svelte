<script>
    import Slide from './Slide.svelte';

    import malwareImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import socialEngineeringImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import denialOfServiceImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import vulnerabilitiesImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import Carousel from './Carousel.svelte';

    const Topics = [
        {slide: {title: "Malware", src: malwareImg, text:`Malware (short for 'Malicious Software') is software whose purpose is to cause damage or disruption on the computer it is installed on, or to allow another party
        to gain unauthorised access to a computer system.`}, 
        content: [
        {title: "Virus", content: `A virus is a self-replicating piece of software that injects its own code into other programs. This malicious code is then run before the infected program is run. Unlike worms, they need
        to be activated by a user first`},
        {title: "Keylogger", content: `A keylogger is a piece of software that records the keystrokes a user makes at a computer and transmits this data to the threat actor. The threat actor can then gain sensitive data, such
        as login credentials.`},
        {title: "Worm", content: `A worm is a self replicating piece of software that replicates itself automatically, without human activity. This makes makes it far more dangerous than a virus. Worms can propagate over
        networks that the victim is connected to. This could cripple an organisation//not done finish writings`},
        {title: "Trojan", content: ""},
        {title: "Spyware", content: ""},
        {title: "Ransomware", content: ""},
        ]},

        {slide: {title: "Social Engineering", src: socialEngineeringImg, text:'Lorem isupm GANNNNNG 2'},
        content: [
        {title: "Phishing", content: ""},
        {title: "Spear Phishing", content: ""},
        {title: "Scareware", content: ""},
        {title: "Baiting", content: ""},
        {title: "Spyware", content: ""},
        {title: "Ransomware", content: ""},
        ]},

        {slide: {title: "Denial-Of-Service", src: denialOfServiceImg, text:'Lorem isupm GANNNNNG 3'}, 
        content: [
        {title: "Virus", content: ""},
        {title: "Keylogger", content: ""},
        {title: "Worm", content: ""},
        {title: "Trojan", content: ""},
        {title: "Spyware", content: ""},
        {title: "Ransomware", content: ""},
        ]},

        {slide: {title: "Vulnerabilites", src: vulnerabilitiesImg, text:'Lorem isupm GANNNNNG 4'}, 
        content: [
        {title: "Virus", content: ""},
        {title: "Keylogger", content: ""},
        {title: "Worm", content: ""},
        {title: "Trojan", content: ""},
        {title: "Spyware", content: ""},
        {title: "Ransomware", content: ""},
        ]},
    ]


    let navigating = true;
    let contentIndex = 0;

    console.log("content: ");
    console.log(Topics[contentIndex].content)

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
                <Carousel CarouselSlides = {Topics[contentIndex].content}/>
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