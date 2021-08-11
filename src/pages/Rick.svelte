<script>
  import { onMount } from 'svelte';

  let endpoint = 'https://rickandmortyapi.com/api/character';
  let query = '';
  let characters = [];

  onMount(async () => {
    const res = await fetch(endpoint);
    const data = await res.json();
    characters = data.results;
  });

  async function search() {
    let filter = `https://rickandmortyapi.com/api/character/?name=${query}`;
    const res = await fetch(filter);
    const data = await res.json();
    characters = data.results;
  }
</script>

<h1 class="title">Rick and Morty</h1>

<div class="contentSearch">
  <input
    type="search"
    bind:value={query}
    on:keydown={search}
    placeholder="Search"
  />
</div>

<main>
  {#each characters as character}
    <figure>
      <picture>
        <img src={character.image} alt="Imagen de {character.name}" loading="lazy" decoding="async">
      </picture>
      <figcaption>
        <section>
          <h1 class="name">{character.name}</h1>
          <h2>{character.species}</h2>
          <h3>{character.status} </h3>
          <span>{character.location.name}</span>
        </section>
      </figcaption>
    </figure>
  {:else}
    <h1 class="title">loading...</h1>
  {/each}
</main>

<style>
  .contentSearch {
    display: flex;
    justify-content: center;
    padding: 0 0 3em 0;
  }

  input[type="search"] {
    width: 250px;
  }

  main {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    /* grid-gap: 10ch; */
  }

  figure {
    display: flex;
    width: 100%;
    max-width: 300px;
    flex-direction: column;
    background: hsl(0 0% 100% / 100%);
    border-radius: 7px;
    overflow: hidden;
  }

  section {
    padding: 0.1em 1em 1em 1em;
    margin-top: -80px;
    background: linear-gradient(hsl(0 0% 100% / 20%),hsl(0 0% 100% / 70%), hsl(0 0% 100% / 100%));
    backdrop-filter: blur(20px);
  }

  .name {
    text-transform: uppercase;
    font-style: italic;
  }

  img {
    max-width: 100%;
  }
</style>