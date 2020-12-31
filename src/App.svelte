<script>
	//ANCHOR add extra fields like year they got blown, known associates and all that
	let icons = [
		{ id: 1, fullName: "David Adeleke", alias: "Davido", careerPath: "Musical Artist", country: "Nigeria", age: 28},
		{ id: 2, fullName: "Ayo Balogun", alias: "Wizkid", careerPath: "Musical Artist", country: "Nigeria", age: 28},
		{ id: 3, fullName: "Chike Ejiofor", alias: "Eji", careerPath: "Actor", country: "Nigeria", age: 35},
		{ id: 4, fullName: "Casper Nyovest", alias: "Casper da Ghost", careerPath: "Musical Artist", country: "South Africa", age: 38 },
		{ id: 5, fullName: "Bright Okpocha", alias: "Basket Mouth", careerPath: "Comedian", country: "Nigeria", age: 40},
		{ id: 6, fullName: "Bukola Elemide", alias: "ASA", careerPath: "Musical Artist", country: "Nigeria", age: 38},
	]

	/*TODO 
	Create a resuable subscription function 
	which needs only the email to get to work 
	- can take on user object later
	*/

	const handleClick = (event, id) => {
		icons = icons.filter(icon => icon.id !== id)
		console.log(event)
	}
</script>

<main>
	
	{#each icons as icon (icon.id)}
		<div class="icons">
			<h1>{icon.fullName}</h1>
			<p>Alias of {icon.alias} is {icon.age}</p>
			<p>Career Path: {icon.careerPath}</p>
			<p>Is from {icon.country}</p>
			<button on:click={(e) => handleClick(e, icon.id)}>
				Delete
			</button>
		</div>
	{:else}
		<p>Loading Icons...</p>
	{/each}
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

	.icons {
		/* text-align: left; */
	}
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 1.5em;
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