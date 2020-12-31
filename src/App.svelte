<script>
	let topic = "Svelte Tutorial"
	let name = "Ade";
	let car = "Benz";
	let color = "red";
	let bgColor = "indigo"
	let reaction = "😐"

	let firstName = "John";
	let lastName = "Doe";
	const changeCar = (carBrand) => {
		car = carBrand;
	}

	//ANCHOR Reactive values 

	$:fullName = `${firstName} ${lastName}`;

	const takeInput = ({ target }) => {
		car = target.value
	}
</script>

<main>
	<h1>{topic}</h1>
	<h4>{fullName} owns a {car}</h4>
	<h4>REACTION is {reaction}</h4>
	<!-- <h4 style="color: {color}">
		{color}
	</h4> -->
	<div class="input_group">
		<label for="">First Name</label>
		<input type="text" bind:value={firstName} >
	</div>
	<div class="input_group">
		<label for="">Last Name</label>
		<input type="text" bind:value={lastName} >
	</div>
	<div class="input_group">
		<label for="">Car Brand</label>
		<input type="text" bind:value={car} >
	</div>
	
	<div class="input_group">
		<label for="">Reaction</label>
		<input type="text" bind:value={reaction} >
	</div>
	<!-- <button on:click={() => changeCar(car)}>
		change car
	</button> -->
	<!-- <div class="box" style="background-color: {bgColor}"></div> -->
	<!-- <input type="text" placeholder="color" bind:value={color}>
	<input type="text" placeholder="color" bind:value={bgColor}> -->

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

	.input_group {
		display: flex;
		flex-direction: column;
	}

	.input_group input {
		border: none;
		border-bottom: 2px solid springgreen;
		outline: 0;
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
		/* text-transform: uppercase; */
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>