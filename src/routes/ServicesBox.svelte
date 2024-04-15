<script>
    const services = [
        {name: "SIEM", mode:"active", content: `SIEM - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},

        {name: "Managed SOC", mode:"inactive", content: `SOC - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},

        {name: "Pentesting", mode:"inactive", content: `PEN - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},

        {name: "Threat Intel", mode:"inactive", content: `Threat Intel - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},

        {name: "Consultancy", mode:"inactive", content: `Consultancy- Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},

        {name: "Standards Compliance", mode:"inactive", content: `Standards Compliance - Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
        remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software 
        like Aldus PageMaker including versions of Lorem Ipsum`},
    ]

    /*I REALLY don't like the whole make mode a string that is either active or inactive, but webdev doesn't seem to like having bools and the like*/
    /*maybe there's a better way, im not sure, I really don't like having a selected attribute as well as a selected variable used in different cases, it feels wrong af*/

    let selected = 0;

</script>


<div class = 'box'>
    <div class = 'left'>
        <h1>
            What we can do for you
        </h1>
        <ul>
            {#each services as {name, mode}, i}
                <li>
                    <button class = {mode} on:click={() => {services[selected].mode = "inactive"; selected = i; mode="active"}}>{name}</button>
                    <!-- This is such fucking spaghetti code man, I hate all of it -->
                    <!-- Like what the fuck, I have such dirty solutions to EVERYTHING, I have two things indicating what is selected, this harder to maintain -->
                    <!-- Im using a string to indicate if something is on or off -->
                    <!-- May the lord strike me down, because I wish I were better, this is one of my worst projects quality-wise -->
                </li>
            {/each}
        </ul>
    </div>

    <div class = 'content'>
        <p>{services[selected].content}</p>
    </div>
</div>

<style>
    div.box {
        display: grid;
        grid-template-columns: 1fr 1fr;
        width: 90%;
        height: 80%;
        border-radius: 1%; 
        /* ^^^^ fix this */
        background-color: rgba(255, 255, 255, 0.235);
        padding: 2em;
    }

    div.left {
        display: flex;
        flex-direction: column;
        border-right: 3px solid #b3b3b33d;
    }

    ul {
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 0.3em;

        list-style-type: none;
    }

    h1 {
        font-size: 2.5em;
    }

    button {
        font-size: 2em;
        background-color: transparent;
        border: none;
        opacity: 50%;
    }

    button:hover {
        opacity: 100%;
    }

    div.content {
        padding: 5%;
        font-size: 1.3em;
    }
    button.active {
        font-weight: bold;
        opacity: 100%;
    }


</style>