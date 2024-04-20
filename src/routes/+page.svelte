<script>
    import Carousel from './Carousel.svelte';
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

<body>
    <Header />

    <HomePage>

        <Slogan />
        
        <CostCounter />
        
        <Hackboxes />
    </HomePage>
    
    <Threats>  
        <h1 class = "header" id="2">Meet some threats</h1>
        <Carousel />
    </Threats>
    
    <WhatWeDo>
        <ServicesBox />
    </WhatWeDo>

    <footer>
        <p>Made by Kenneth Knight</p>

    </footer>
</body>

<style>
    body {
        /* background-image: linear-gradient(90deg, #010B26, #611226); */
        
        display: grid;
        grid-template-columns: 1fr;
    }

    h1 {
        color: black
    }

    footer p {
        color: black;
    }
</style>




