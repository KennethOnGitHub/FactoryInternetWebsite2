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

</script>

<div>
    {#each Slides as slide}
        <Slide {...slide}/>
    {/each}
</div>

<style>
    div {
        display: flex;
        justify-content: center;
    }
</style>
