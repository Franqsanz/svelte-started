<script>
  const callApi = async () => {
    const response = await fetch('https://randomfox.ca/floof/')
    return response.json()
  }

	const apiImage = callApi();
</script>

<h1>Fox</h1>

{#await apiImage then data}
	<div class="card">
		<img src={data.image} alt="Fox" />
		Link:
		<a href={data.link}>{data.link}</a>
	</div>
{/await}

<style>
	.card {
		max-width: 500px;
		padding: 0.7em;
		background:#fdb197;
		margin: 0 auto;
		border-radius: 7px;
	}

	img {
		max-width: 100%;
		object-fit: cover;
		border-radius: 7px;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 5em;
		font-weight: 100;
		text-align: center;
	}
</style>