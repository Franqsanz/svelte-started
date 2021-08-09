<script>
	import { Router, Route, Link } from "svelte-routing";
	import Home from './pages/Home.svelte';
	import Random from './pages/Random.svelte';
	import Rick from './pages/Rick.svelte';

  export let url = "";
</script>

<Router url={url}>
	<nav>
		<ul>
			<li><Link to="/">Home</Link></li>
			<li><Link to="random">Random Phrases</Link></li>
			<li><Link to="rick">Rick</Link></li>
		</ul>
	</nav>
	<Route path="random" component={Random} />
	<Route path="rick" component={Rick} />
	<Route path="/"><Home /></Route>
</Router>

<style>
	nav	{
		display: flex;
		justify-content: center;
		font-weight: 700;
		/* background: #0f2944; */
	}

	ul {
		display: flex;
		padding-inline-start: 0;
	}

	li {
		list-style: none;
		padding: 0.5em;
	}
</style>