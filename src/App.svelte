<script>
	import Model from "./Model.svelte";
	import AddPersonForm from "./AddPersonForm.svelte"

	let showModel = false 
	let people = [
		{name: 'Jukis', beltColor: 'black', age: '18', id: '1'},
		{name: 'Yuri', beltColor: 'blue', age: '19', id: '2'}
	]

	const handleClick = (id) => {
		people = people.filter((person) => person.id != id)
	}

	const toggleModel = () => {
		showModel = !showModel
	} 
</script>

<Model {showModel} on:click={toggleModel}>
	<AddPersonForm></AddPersonForm>
</Model>

<main>
	<button on:click={toggleModel}>Show Model</button> 
	{#each people as person (person.id)}
	<div>
		<h4>{person.name}</h4>
		<p>{person.age} years old, {person.beltColor} belt</p>
		<button on:click={() => {
			handleClick(person.id)}}>delete</button>
	</div>
	{:else}
	<p>There are no people to show...</p>
	{/each}
</main>

<style>
	main {
		text-align: left;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>