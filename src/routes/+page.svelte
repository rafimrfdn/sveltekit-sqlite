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
  <title>Here's a title!</title>
</svelte:head>

<main class="w-[95%] max-w-2xl mx-auto mt-48">
  <h1 class="text-3xl font-bold">
    Menampilkan data superhero dari SQlite database local
  </h1>
  <p>Temukan superhero mu disini!</p>
  <input
    class="p-2 border border-2 border-blue-700 rounded-full pl-5 mt-5"
    type="search"
    autocomplete="off"
    placeholder="Search"
    bind:value
  />
  <SuperHeroes {items} />
</main>
