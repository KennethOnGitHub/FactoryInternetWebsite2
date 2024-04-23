<script>

    import CostCounter from './CostCounter.svelte';
    import Hackboxes from './Hackboxes.svelte';
    import Header from './Header.svelte';
    import HomePage from './HomePage.svelte';
    import MajorHack from './MajorHack.svelte';
    import ServicesBox from './ServicesBox.svelte';
    import Slogan from './Slogan.svelte';
    import Threats from './Threats.svelte';
    import WhatWeDo from './WhatWeDo.svelte';
    import './reset.css'
    import './styles.css'
</script>

<svelte:head>
    <title>Cybersecurity - Factory Internet</title> 
    <link rel="icon" href="https://www.factoryinternet.co.uk/wp-content/uploads/2021/03/cropped-Globe-w-white-circle-32x32.png">
</svelte:head>
<body>
    <Header />

    
    <HomePage>

        <Slogan />
        
        <CostCounter />
        
        <Hackboxes />
    </HomePage>
    
    <Threats />  
    
    <WhatWeDo>
        <ServicesBox />
    </WhatWeDo>

    <footer>
        <h2>
            Contact Us
        </h2>
        <p>High Weald House, Bexhill-On-Sea, East Sussex, TN39 5ES </p>
        <a href="mailto:sales@factoryinternet.co.uk">sales@factoryinternet.co.uk</a>
        <p>(+44)1424 540175</p>
        <a href = 'www.factoryinternet.co.uk'>www.factoryinternet.co.uk</a>

        <p>Webpage made by Kenneth Knight</p>

    </footer>
</body>

<style>
    body {
        /* background-image: linear-gradient(90deg, #010B26, #611226); */
        
        display: grid;
        grid-template-columns: 1fr;
        overflow-x: hidden;
    }

    footer{
        background-color: darkgrey;
        padding: 1em;
    }

    h2 {
        text-decoration: underline;
    }
</style>




