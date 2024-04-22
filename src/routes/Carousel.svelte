<script>
    import rightArrow from '$lib/assets/right-arrow.svg';

    export let CarouselSlides = [];
    console.log("sides: ")
    console.log(CarouselSlides);

    let position = 0;
    const displayedSlides = 4;
</script>

<div class= 'carousel'>
    <button on:click={() => {if (position > 0) {position -= 1}}}>
        <img class = 'left' src = {rightArrow} alt = 'Left'>
    </button>

    <div class = 'slide-container'>
        {#each CarouselSlides.slice(position, position + displayedSlides) as slide}
            <div class = 'slide'>
                <h3>{slide.title}</h3>
                <p>{slide.content}</p>
            </div>
        {/each}
    </div>

    <button on:click={() => {if (position < CarouselSlides.length - displayedSlides) {position += 1}}}>
        <img src = {rightArrow} alt = 'Right'>
    </button>
</div>

<style>
    .carousel {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 80%;
    }


    .slide-container {
        display: grid;

        grid-template-columns: repeat(4, 1fr);
        grid-gap: 1em;

        height: 100%;
        width: 80%;
    }

    .slide {
        height: 100%;
        border-radius: 5px;
        padding: 1em;
        border: solid white 2px;
        background-color: #ffffff30;
    }

    button {
        height: 40px;
        width: 40px;
        background-color: transparent;
        border: none;
        cursor: pointer;
    }

    .left {
        transform: rotate(180deg);
    }


</style>