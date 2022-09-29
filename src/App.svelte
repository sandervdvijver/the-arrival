<script>
	import { onMount } from 'svelte';
	import list from './list.json';

	let locations = list.locations;
	let atmospheres = list.atmospheres;
	let characters = list.characters;

	let location, atmosphere, character;

	onMount(async () => {
		generateItems();
	})

	function pickItemFrom(list) {
		var chosenNumber = Math.floor(Math.random() * list.length);
		var el = list[chosenNumber];
		return el;
	}
	
	function generateItems() {
		location = pickItemFrom(locations);
		atmosphere = pickItemFrom(atmospheres);
		character = pickItemFrom(characters);
	}

	function handleClick() {
		generateItems();
	}
</script>

<main>
	<ul>
		<li>{location}</li>
		<li>{atmosphere}</li>
		<br>
		<li>{character}</li>
	</ul>
	<button on:click={handleClick}>Refresh</button>
</main>

<style>
	main {
    	margin: 2rem auto;
		font-size: 36px;
		font-size: clamp(30px, 4vw, 36px);
	}
	ul {
		padding-left: 0;
		margin-top: 0;
		padding-top: 0;
	}
	li {
		list-style-type: none;
		padding: 0;
		margin: 0;
	}
	button {
		font-size: 75%;
		cursor: pointer;
	}
</style>