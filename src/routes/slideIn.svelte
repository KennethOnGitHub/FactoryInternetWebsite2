<script>
    import { onMount } from "svelte";
  
    export let root = undefined;
    export let isInViewProp = false;
  
    let isInView = false;
    let observer;
    let element;
  
    $: isInView, (isInViewProp = isInView);
  
    const onChangeVisibility = (e) => {
      isInView = e[0].isIntersecting;
    };
  
    onMount(() => {
      let options = {
        root: root,
      };
  
      observer = new IntersectionObserver(onChangeVisibility, options);
      observer.observe(element);
    });
  </script>
  
  <div class= {isInViewProp? "" : "out"} bind:this={element}>
    <slot/>
  </div>
  
  <style>
      div {
        transition: transform 1s, opacity 1s;
      }
      .out {
        opacity: 0;
        transform: translateX(100px)
      }

  </style>

