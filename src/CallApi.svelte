<script>
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
    <div class="card">
      <img src={character.image} alt="">
      <div class="info">
        <h1>{character.name}</h1>
        <h2>{character.species}</h2>
        <h3>{character.status} </h3>
        <span>{character.location.name}</span>
      </div>
    </div>
  {:else}
    <h1>loading...</h1>
  {/each}
</main>

<style>
  .title {
    text-align: center;
    color: #ff3e00;
    font-size: clamp(2.5rem, 7vw, 6rem);
  }

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