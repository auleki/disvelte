<script>
	let name = "Ade";
	let car = "Benz";
	const changeCar = (carBrand) => {
		car = carBrand;
	}

	const takeInput = ({ target }) => {
		car = target.value
	}
</script>

<main>
	<h1>{car}</h1>
	<button on:click={() => changeCar("toyota")}>
		change car
	</button>
	<input type="text" on:input={takeInput} value={car}>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		/* text-transform: uppercase; */
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>