<script>
	let name = "Ade";
	let car = "Benz";
	let color = "red";
	let bgColor = "indigo"
	const changeCar = (carBrand) => {
		car = carBrand;
	}

	//ANCHOR comments will come in useful

	const takeInput = ({ target }) => {
		car = target.value
	}
</script>

<main>
	<h1>{car}</h1>
	<h4 style="color: {color}">
		{color}
	</h4>
	<button on:click={() => changeCar("toyota")}>
		change car
	</button>
	<div class="box" style="background-color: {bgColor};"></div>
	<input type="text" bind:value={car} >
	<input type="text" placeholder="color" bind:value={color}>
	<input type="text" placeholder="color" bind:value={bgColor}>

	<!-- <input type="text" on:input={takeInput} value={car}> -->

</main>

<style>
	main {
		text-align: center;
		display: flex;
		align-items: center;
		flex-direction: column;
		justify-content: space-evenly;
		align-items: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.box {
		height: 10em;
		width: 10em;
		
	}

	h1 {
		color: #ff3e00;
		/* text-transform: uppercase; */
		font-size: 4em;
		font-weight: 100;
	}

	h4 {
		font-size: 2em;
		font-weight: 100;
		text-transform: uppercase;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>