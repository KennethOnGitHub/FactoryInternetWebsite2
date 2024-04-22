<script>
    import Slide from './Slide.svelte';

    import malwareImg from '$lib/assets/1200px-Virus_malware_hazard_icon.png'
    import socialEngineeringImg from '$lib/assets/social-engineering-2.png'
    import denialOfServiceImg from '$lib/assets/denial-of-service.svg'
    import vulnerabilitiesImg from '$lib/assets/bug.svg'
    import Carousel from './Carousel.svelte';

    //this should probably be stored elsewhere, like in a JSON file, but thats a refactor for later
    const Topics = [
        {slide: {title: "Malware", src: malwareImg, text:`Malware (short for 'Malicious Software') is software whose purpose is to cause damage or disruption on the computer it is installed on, or to allow another party
        to gain unauthorised access to a computer system.`}, 
        content: [
        {title: "Virus", content: `A virus is a self-replicating piece of malware that injects its own code into other programs. This malicious code is then run before the infected program is run. Unlike worms, they need
        to be activated by a user first`},
        {title: "Keylogger", content: `A keylogger is a piece of malware that records the keystrokes a user makes at a computer and transmits this data to the threat actor. The threat actor can then gain sensitive data, such
        as login credentials.`},
        {title: "Worm", content: `A worm is a self replicating piece of malware that replicates itself automatically, without human activity. This makes makes it far more dangerous than a virus. Worms can propagate over
        networks that the victim is connected to. This could cripple an organisation if it is able to spread across its network from just one compromised device.`},
        {title: "Trojan", content: `A Trojan, whose name comes from the classic greek myth of the Trojan Horse, is a piece of malware that is disguised as legitimate piece of software, such as a tool/app. Once executed, it begins
        to cause damage, for example, it could act as spyware or ransomware.`},
        {title: "Spyware", content: `Spyware is a type of malware that gathers information from victims' devices. It records and sends to threat actors data such as your login credentials, personal information, your emails,
        and your activities on the device.`},
        {title: "Ransomware", content: `Ransomware is a type of malware that locks victims out of their device/data, promising that victims would regain access to it after paying a sum of money. This is usually done through 
        encrypting the files on the device and demanding money in exchange for decrypting the data. Threat actors may also threaten to leak the data on the compromised device as well.`},
        ]},

        {slide: {title: "Social Engineering", src: socialEngineeringImg, text:'Social engineering is hacking achieved through manipulating people into giving a threat actor access to a computer system'},
        content: [
        {title: "Phishing", content: `Phishing is when a threat actor sends electronic communication (e.g. an email or a text message) with the intent of tricking the victim into handing over private information or installing
        malware. OFten the email/text message attempts to trick victims into clicking a link that brings them to a website impersonating a legitimate organisation's website (e.g. a bank or the government).`},
        {title: "Spear Phishing", content: `Spear phishing is a variant of phishing which targets a single person or organisation. The communications are more personalised and tailored to maximise the chance of deceiving the targets.`},
        {title: "Scareware", content: `Scareware is a social engineering technique that involves inciting fear in victims (e.g. creating a pop-up advert claiming that there is a virus on their device) to manipulate victims into downloading
        malware or bloatware.`},
        {title: "Baiting", content: `Unlike Scareware, baiting involves a threat actor using a positive 'bait' to deceive victims into installing malware or giving over sensitive information. For example, threat actors may create
        pop-up adverts claiming that a user has won a free IPad, however, the pop-up is a link to install malware. `},
        {title: "Tailgaiting", content: `Also known as piggybacking, tailgating is one of the most 'physical' approaches to social engineering. When tailgating, a threat actor attempts to gain access to a physical location that 
        they do not have authorisation to access. This is often done through entering just behind someone authorised to enter or by pretending to need access (e.g. a delivery person).`},
        {title: "Pretexting", content: `Pretexting is a technique used by threat actors to manipulate victims into sharing sensitive data by fabricating scenarios (e.g. a threat actor may impersonate other personnel within an organisation needing help)
        that make the attacker seem more trustworthy.`},
        ]},

        {slide: {title: "Denial-Of-Service", src: denialOfServiceImg, text:'Denial of Service cyberattack involves a computer or network is flooded with trafic or sent data that causes a crash. This makes the service unusable for users. '}, 
        content: [
        {title: "Dos", content: "In a regular Denial of Service attack, a single device overwhelms a target with fake traffic, causing it to run out of computing resources and making it unusable by legitimate users."},
        {title: "DDos", content: `In a Distributed Denial of Service attack, many computers working together as a single botnet flood a target with fake traffic to make in inaccesible. A distributed attack is harder 
        to block due to the large number of devices involved`},
        {title: "Application Layer Attack", content: `A Denial of Service attack may target weaknesses in the application layer (the topmost layer in OSI and TCP/IP model). For example, a threat actor may create a program to create
        a flood of HTTP requests; HTTP requests are simple to create, but take substantially more resources to process and respond to.`},
        {title: "State-Exhaustion Attack", content: `In a state-exhaustion attack, also referred to as a protocol attack, threat actors leverage weaknesses in the network and transport layer. For example, they make generate a large number of
        TCP Initial Connection Requests, the target then repondsto these requests and then waits for the attacker to respond in return, however, the attacker never responds, wasting the targets resources.`},
        ]},

        {slide: {title: "Vulnerabilites", src: vulnerabilitiesImg, text:'Lorem isupm GANNNNNG 4'}, 
        content: [
        {title: "Injection", content: `In an injection attack, such as a buffer overflow attack or a SQL injection attack, a threat actor submits a malicious input that containing data to be interpreted as instructions by 
        a target program. THe program then runs these instructions, which often cause data theft or in egregious scenarios, a total compromise of a system.`},
        {title: "Zero-Day", content: `A zero-day vulnerability is a flaw in a program/system that is discovered and used by threat actors before it is known by owners of the system.`},
        {title: "Out-of-Date Software", content: 'Software used by an organisation that is not regularly kept up-to-date may contain vulnerabilities easily exploited by threat actors.'},
        {title: "Software Misconfiguration", content: `Software used within a computer system have settings to dictate what functionality is enabled, a misconfiguration could lead to an integral security feature being disabled or a exploitable
        feature being enabled.`},
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