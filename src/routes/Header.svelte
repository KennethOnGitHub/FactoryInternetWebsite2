<script>
    import logo from '$lib/assets/Factory-Internet-Logo-2019-220x47.webp';

    let y;

</script>

<header>
    <a href="https://www.factoryinternet.co.uk/"> <img src =  {logo} alt = 'Factory Internet'> </a>
    <nav>
        <a href="#1" class = {y < 780 ? "highlighted" : ""}>Home</a>
        <a href="#2" class = {780 < y && y < 780 + 800 ? "highlighted" : ""}>Threats</a>
        <a href="#3" class = {780 + 800 <= y ? "highlighted" : ""}>What We Do</a>
    </nav>
</header>

<style>
    header {
        position: fixed;
        display: flex;
        width: 100%;
        background-color: #086ad8;
        padding: 3px 0px 3px 20px;
        z-index: 2;
    }

    nav {
        display: flex;
        flex-grow: 1;
        justify-content: space-evenly;
        align-items: center;
        color: white;
    }

    a {
        text-decoration: none;
        padding: 5px;
        border-radius: 4px;
        opacity: 80%;
    }

    a:hover {
        opacity: 100%;
    }

    .highlighted {
        background-color: white;
        color: black;
    }
</style>

<svelte:window bind:scrollY={y} />