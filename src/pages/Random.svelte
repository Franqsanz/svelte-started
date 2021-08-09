<script>
  let phrases = [
    {
      phrase: '"El único modo de hacer un gran trabajo es amar lo que haces - Steve Jobs"'
    },
    {
      phrase: '"Nunca pienso en las consecuencias de fallar un gran tiro… cuando se piensa en las consecuencias se está pensando en un resultado negativo - Michael Jordan"'
    },
    {
      phrase: '"El dinero no es la clave del éxito; la libertad para poder crear lo es - Nelson Mandela"'
    },
    {
      phrase: '"Cuanto más duramente trabajo, más suerte tengo - Gary Player"'
    },
    {
      phrase: '"La inteligencia consiste no sólo en el conocimiento, sino también en la destreza de aplicar los conocimientos en la práctica - Aristóteles"'
    },
    {
      phrase: '"El trabajo duro hace que desaparezcan las arrugas de la mente y el espíritu - Helena Rubinstein"'
    },
    {
      phrase: '"Cuando algo es lo suficientemente importante, lo haces incluso si las probabilidades de que salga bien no te acompañan - Elon Musk"'
    },
    {
      phrase: '"Escoge un trabajo que te guste, y nunca tendrás que trabajar ni un solo día de tu vida - Confucio"'
    },
    {
      phrase: '"Un sueño no se hace realidad por arte de magia, necesita sudor, determinación y trabajo duro - Colin Powell"'
    },
    {
      phrase: '"Cuéntamelo y me olvidaré. enséñamelo y lo recordaré. involúcrame y lo aprenderé - Benjamin Franklin"'
    },
    {
      phrase: '"La lógica te llevará de la a a la z. la imaginación te llevará a cualquier lugar - Albert Einstein"'
    }
	];

  let newPhrases = null;
  let data = JSON.parse(localStorage.getItem("phrases"));

  if (!data) {
    localStorage.setItem('phrases', JSON.stringify(phrases));
  }

  let phrase = data[Math.floor(Math.random() * data.length)];

  function save(newPhrases) {
    localStorage.setItem('phrases', JSON.stringify(newPhrases));
  }

  function addPhrases() {
		if (!newPhrases) return;

    phrases = [...phrases,
      {
        phrase: newPhrases
      }
    ];

    save(phrases);

    newPhrases = null
  }

  function handleSubmit(e) {
    e.preventDefault();
  }

</script>

<h1 class="title">Random Phrases</h1>

<p>{phrase.phrase}</p>

<form on:submit={handleSubmit}>
  <textarea bind:value={newPhrases} placeholder="Add Phrases" />
  <button on:click={addPhrases}>Add Phrases</button>
</form>

<style>
  p {
    width: 100%;
    max-width: 400px;
    margin: 0 auto;
    color: #fafafa;
    font-size: clamp(1.125rem, 3vw, 1.563rem);
    line-height: 1.66;
    font-style: italic;
    text-align: center;
    padding: 1em 0 2em 0;
  }

  form {
    max-width: 300px;
    display: flex;
    margin: 0 auto;
    flex-direction: column;
    box-sizing: border-box;
    padding: 3em 0 3em 0;
  }

  button, textarea {
    border-radius: 7px;
  }

  button {
    padding: 1em;
    margin: 2ch 0 0 0;
    background: #ff3e00;
    color: #000000;
    font-weight: 700;
    letter-spacing: 3px;
  }

  button:active {
    background: #c73200;
    color: white;
  }

  textarea {
    padding: 0.5em;
    font-size: 1.125rem;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
</style>