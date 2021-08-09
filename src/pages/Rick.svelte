<script>
  let url = 'Rick and Morty';

  import { onMount } from 'svelte';

  let endpoint = 'https://rickandmortyapi.com/api/character';
  let characters = [];

  onMount(async () => {
    const res = await fetch(endpoint);
    const data = await res.json();
    characters = data.results;
  });
</script>

<h1 class="title">Rick and Morty</h1>

<main>
  {#each characters as character}
    <figure class="card">
      <img src={character.image} alt="Imagen de {character.name}" loading="lazy" decoding="async">
      <figcaption class="info">
        <h1>{character.name}</h1>
        <h2>{character.species}</h2>
        <h3>{character.status} </h3>
        <span>{character.location.name}</span>
      </figcaption>
    </figure>
  {:else}
    <h1 class="title">loading...</h1>
  {/each}
</main>

<style>
  main {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    grid-gap: 1.5em;
  }

  .card {
    display: flex;
    width: 100%;
    max-width: 300px;
    flex-direction: column;
    background: #ececec;
    border-radius: 7px;
    overflow: hidden;
  }

  img {
    max-width: 100%;
  }

  .info {
    padding: 0 1em 1em 1em;
  }
</style>