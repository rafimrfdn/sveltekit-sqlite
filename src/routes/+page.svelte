<script>
import SuperHeroes from "$lib/components/SuperHeroes.svelte";
let items = [];
let value = "";
const description = "Here's my description!";

async function update(value) {
    if (value.trim().length > 0) {
        const response = await fetch(`/heroes?q=${value.trim()}`);
        items = await response.json();
    } else {
        items = [];
    }
}

$: update(value);
</script>

<svelte:head>
  <meta name="description" content={description} />
  <title>Super Heroes Database</title>
</svelte:head>

<main class="">
  <h1 class="">
    Menampilkan data superhero dari SQlite database local
  </h1>
  <p>Temukan superhero mu disini!</p>
  <input
    class=""
    type="search"
    autocomplete="off"
    placeholder="Search"
    bind:value
  />
  <SuperHeroes {items} />
</main>
