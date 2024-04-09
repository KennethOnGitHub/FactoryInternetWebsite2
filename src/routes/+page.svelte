<script>
    import CostCounter from './CostCounter.svelte';
    import Hackboxes from './Hackboxes.svelte';
    import Header from './Header.svelte';
    import MajorHack from './MajorHack.svelte';
    import Slogan from './Slogan.svelte';
    import './reset.css'
    import './styles.css'
</script>

<body>
    <Header />
    <Slogan />
    
    <CostCounter />

    
    <Hackboxes />

    <h1 id="2">Threats</h1>
    <h1 id="3">What we do</h1>
</body>

<style>
    body {
        background-image: linear-gradient(90deg, #010B26, #611226);
        
        display: grid;
        gap: 1em;
        grid-template-columns: 1fr;
    }
</style>




