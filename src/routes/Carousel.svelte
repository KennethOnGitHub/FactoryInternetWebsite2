<script>
    import Slide from './Slide.svelte';

    import malwareImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import socialEngineeringImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import denialOfServiceImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    import vulnerabilitiesImg from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp'
    
    const malware = {title: "Malware", src: malwareImg, text:'Lorem isupm GANNNNNG 1 The industrial revolution and its consequences were realllll interesting guys'}
    const socialEngineering = {title: "Social Engineering", src: socialEngineeringImg, text:'Lorem isupm GANNNNNG 2'}
    const denialOfService = {title: "Denial-Of-Service", src: denialOfServiceImg, text:'Lorem isupm GANNNNNG 3'}
    const vulnerabilities = {title: "Vulnerabilites", src: vulnerabilitiesImg, text:'Lorem isupm GANNNNNG 4'}
    
    const Slides = [malware, socialEngineering, denialOfService, vulnerabilities]

    let state = "nav-mode";
    console.log("test");

</script>

<div class = {state + " container"}>
    <nav>
        {#each Slides as slide}
        <button on:click={() => state = slide.title + "-mode"}>
            <Slide {...slide}/>
        </button>       
    {/each}
    </nav>

    <div class = 'wrapper'>
        <div class = 'content'>
            <p>
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled
                it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of
                Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
            </p>
        </div>
    </div>

</div>

<style>
    .container {
        display: grid;
        grid-template-columns: 1fr 1fr;
        width: 200vw;
        height: 100%;
        /* not sure why height 100% works tbh, no time to figure it out tho */

        position: relative;
        left: -100%;
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

    .nav-mode {
        left:0;
    }
</style>
