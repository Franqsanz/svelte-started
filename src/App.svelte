<script>
	import { Router, Route, Link } from "svelte-routing";
	import Home from './pages/Home.svelte';
	import Phrases from './pages/Phrases.svelte';
	import Rick from './pages/Rick.svelte';

  export let url = "";
</script>

<Router url={url}>
	<header>
		<nav>
			<ul>
				<li><Link to="/">Home</Link></li>
				<li><Link to="phrases">Phrases</Link></li>
				<li><Link to="rick">Rick</Link></li>
			</ul>
		</nav>
	</header>
	<Route path="phrases" component={Phrases} />
	<Route path="rick" component={Rick} />
	<Route path="/"><Home /></Route>
</Router>

<style>
	nav	{
		display: flex;
		justify-content: center;
		background: #0f29447d;
	}

	ul {
		display: flex;
		padding-inline-start: 0;
	}

	li {
		list-style: none;
		padding: 0 0.5em 0 0.5em;
	}
</style>