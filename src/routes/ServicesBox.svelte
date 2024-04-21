<script>
    const services = [
        {name: "SIEM", mode:"active", content: `Security Information and Event Management, shortened to SIEM and pronounced "sim", is software that locates threats by pooling in data from various sources in an IT system and 
        analysing the data to find suspicious patterns to locate possible threats. Security teams working for an organisation can therefore respond to threats more quickly. SIEM is integral for protecting systems; hundreds to thousands of 
        unconnected alerts could be generated from isolated tools, making it difficult for security teams to locate and fight the real threats.`},

        {name: "Managed SOC", mode:"inactive", content: `A Security Operations Center is a team of cybersecurity professionals that continuously monitors and manages the security of an organisations IT systems. A SOC works non-stop
        to detect and prevent threats before they cause harm, investigate suspicious activity, and respond to incidents if they do happen. After any incidents, a SOC team works to patch vulnerabilities in a system and restore it
        to operational condition. \n
        Using an external Managed SOC compared to an in-house SOC allows your organisation to focus on its primary goals, leaving the burden of managing security to the experts.`},
        // no clue why the newline doesn't work, no time to figure it out

        {name: "Pentesting", mode:"inactive", content: `Penetration testing is a method of identifying critical security flaws in a system by simulating a cyberattack on a system. By getting into the shoes of threat actors,
        cybersecurity experts can find vulnerabilities before threat actors do. This could, for example, involve testing inputs of systems to find vulnerabilities to injection attacks or attempting to social engineer members of
        your organisation to find 'human' vulnerabilities.`},

        {name: "Threat Intel", mode:"inactive", content: `Threat Intelligence is detailed information on threat actors used by organisations to proactively fight threats. This information includes threat actors' motivations,
        targets, attack patterns, and attack techniques. Threat Intel empowers organisations to make decisions guided by data. With data on threat actors' possible next moves, organisations 
        can be more active in the fight for security.`},

        {name: "Consultancy", mode:"inactive", content: `Factory can aide your IT teams as they build systems, giving direction on how to effictively secure systems from attacks //write more`},

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