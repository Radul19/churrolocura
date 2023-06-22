<script>
  import { onMount } from "svelte";
  import loading from '../public/loading.gif'

  //   import { browser } from "$app/environment";
  let iw;
  let ih;
  onMount(() => {
    let desktop = iw > ih && true;

    if (desktop) {
        console.log('waaaaat')
        window.location.href = "/desktop/home";
    } else {
        console.log('waaaaat2')
      window.location.href = "/mobile/home";
    }
  });
</script>

<svelte:window bind:innerWidth={iw} bind:innerHeight={ih} />
<div class="">
    <!-- <p>Loading...</p> -->
    <img src={loading} alt="laoding">
</div>
<!-- <p>Visit <a href="/mobile/home">Mobile folder</a> to read the documentation</p> -->

<style>
    div{
        height: 100vh;
        width: 100vw;
        box-sizing: border-box;
        background-color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    /* p{
        margin: 0px;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        text-align: center;
    } */
    img{
        /* width: 100%; */
        max-width: 320px;
    }
</style>