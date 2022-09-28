<script>
	let locations = ["in a peaceful valley", "in an anonymous suburb", "at a crossroads", "at a remote outpost", "in a fishing village", "at a train station", "in a busy inn", "at the grounds of an enormous factory", "at a border crossing", "at a hut in the forest", "at an old stone cabin in the mountains", "in a solemn courtyard", "at a modernist mansion overlooking the city", "in a crowded harbour", "at an ancient tree", "in a quiet provincial town", "at a market square", "in a hotel past its glory days", "in a roadside restaurant", "in a dusty bookstore"];
	let atmospheres = ["on an overcast day", "in the middle of a starless night", "during summer solstice", "in the fog", "in winter", "during first snow", "in the early morning", "in autumn rain", "on a particularly hot day", "in stormy weather", "under moonlight", "after a long absence", "at dusk", "weary from travelling", "cast in shadows", "shrouded in smoke", "lit by a single light source"];
	let characters = ["a giant arrives", "a stranger arrives", "a large bird arrives", "a band of outsiders arrives", "a peculiar child arrives", "a cloaked figure arrives", "two travellers arrive", "a hurried messenger arrive", "a private investigator arrives", "a hunter arrives", "a large animal arrives", "a family of four arrives", "an adolescent arrives", "a travelling saleswoman arrives", "a travelling salesman arrives", "an unwelcome guest arrives", "an outlaw arrives", "a bearer of bad news arrives"];
	let count = 0;

	function handleClick() {
		count += 1;
	}

	function pickItem(list,el) {
		var chosenNumber = Math.floor(Math.random() * list.length);
    	el = list[chosenNumber];
    	return el;
	}
</script>

<main>
	<ul>
		<li>{pickItem[locations]}</li>
		<li>{pickItem[atmospheres]}</li>
		<li>{pickItem[characters]}</li>
	</ul>
	<button on:click={handleClick}>Refresh</button>
</main>

<style>
	main {
    	width: 50vw;
    	margin: 0 auto;
	}
	ul {
		padding-left: 0;
	}
	li {
		list-style-type: none;
		padding: 0;
		margin: 0;
	}
</style>