<script>
  let texts = [
    '"El único modo de hacer un gran trabajo es amar lo que haces - Steve Jobs"',
    '"Nunca pienso en las consecuencias de fallar un gran tiro… cuando se piensa en las consecuencias se está pensando en un resultado negativo - Michael Jordan"',
    '"El dinero no es la clave del éxito; la libertad para poder crear lo es - Nelson Mandela"',
    '"Cuanto más duramente trabajo, más suerte tengo - Gary Player"',
    '"La inteligencia consiste no sólo en el conocimiento, sino también en la destreza de aplicar los conocimientos en la práctica - Aristóteles"',
    '"El trabajo duro hace que desaparezcan las arrugas de la mente y el espíritu - Helena Rubinstein "',
    '"Cuando algo es lo suficientemente importante, lo haces incluso si las probabilidades de que salga bien no te acompañan - Elon Musk"',
    '"Escoge un trabajo que te guste, y nunca tendrás que trabajar ni un solo día de tu vida - Confucio"',
    '"Un sueño no se hace realidad por arte de magia, necesita sudor, determinación y trabajo duro - Colin Powell"',
    '"Cuéntamelo y me olvidaré. enséñamelo y lo recordaré. involúcrame y lo aprenderé - Benjamin Franklin "',
    '"La lógica te llevará de la a a la z. la imaginación te llevará a cualquier lugar - Albert Einstein"'
	];

	let text = texts[Math.floor(Math.random() * texts.length)];

</script>

<p>{text}</p>

<style>
  p {
    width: 100%;
    max-width: 500px;
    margin: 0 auto;
    color: #fafafa;
    font-size: clamp(1.125rem, 3vw, 1.563rem );
    line-height: 1.66;
    font-style: italic;
    text-align: center;
    padding: 1em 0 2em 0;
  }
</style>