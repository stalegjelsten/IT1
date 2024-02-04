<script>
	// Oppgave 6-21a) http://deckofcardsapi.com/api/deck/new/draw/?count=1
	let antall = 1;
	let laster = false;
	let kortstokk = [];

	// let trekkKort = async () => {
	// 	laster = true;
	// 	let data = await fetch('http://deckofcardsapi.com/api/deck/new/draw/?count=' + antall);

	// 	let json = await data.json();
	// 	kortstokk = json.cards;
	// 	laster = false;
	// };

	let trekkKort = () => {
		const url = 'http://deckofcardsapi.com/api/deck/new/draw/?count=' + antall;
		fetch(url)
			.then((response) => response.json())
			.then((data) => (kortstokk = data.cards));
		laster = false;
	};

	// denne linjen gjør at vi kjører "trekkKort" når "antall" endrer seg
	$: antall, trekkKort();
</script>

<label for="antall">Antall kort: </label><input
	type="number"
	min="0"
	id="antall"
	bind:value={antall}
	size="3"
/>
{#if laster}
	Laster...
{/if}

<h1>Kortstokk</h1>
<main>
	{#each kortstokk as kort}
		<div>
			{kort.value + ' of ' + kort.suit}
			<img src={kort.image} alt={kort.value + ' of ' + kort.suit} />
		</div>
	{/each}
</main>

<style>
	main {
		/* det kan være fint å vise kortene som et rutenett */
		display: grid;
		grid-template-columns: repeat(5, 1fr);
	}
	div {
		text-align: center;
		font-weight: bold;
		font-size: 120%;
	}
	div > img {
		width: 100%;
	}
</style>
