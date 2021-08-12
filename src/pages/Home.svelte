<script>
	const callApi = async () => {
	const response = await fetch('https://randomfox.ca/floof/')
	return response.json()
  }

	const apiImage = callApi();
</script>

<h1 class="title">FOX</h1>
{#await apiImage then data}
	<div class="card">
		<img src={data.image} alt="Fox" decoding="async" />
	</div>
{/await}

<style>
  .card {
		max-width: 500px;
		padding: 1em;
		margin: 6ch auto;
	}

	img {
		max-width: 100%;
		object-fit: cover;
		border-radius: 7px;
	}
</style>