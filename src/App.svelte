<script>
  import logo from "./assets/svelte.png";
  import Counter from "./lib/Counter.svelte";

  let beltColor = "black";
  let firstname = "Anh";
  let lastname = "Le";

  // Reactive
  $: fullname = `${firstname} ${lastname}`
  $: {
    console.log(beltColor)
    console.log(fullname)
  }

  const handleClick = () => {
    beltColor = "orange";
  };
  const handleInput = (e) => {
    beltColor = e.target.value;
  };
</script>

<main>
  <img src={logo} alt="Svelte Logo" />
  <h1>Hello world!</h1>

  <Counter />
  <p style="color:{beltColor}">{fullname} - {beltColor}</p>
  <!-- <button on:click={handleClick}>Update belt color</button> -->
  <!-- <input type="text" on:input={handleInput} value={beltColor}> -->
  <input type="text" bind:value={firstname} />
  <input type="text" bind:value={lastname} />
  <input type="text" bind:value={beltColor} />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  img {
    height: 16rem;
    width: 16rem;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
