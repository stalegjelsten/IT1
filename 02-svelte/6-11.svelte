<script>
	let grunnstoff1 = {
		navn: 'Hydrogen',
		symbol: 'H',
		atomnummer: '1',
		tilstand: 'gass'
	};

	let grunnstoff2 = {
		navn: 'Oksygen',
		symbol: 'O',
		atomnummer: '8',
		tilstand: 'gass'
	};

	let grunnstoff3 = {
		navn: 'Karbon',
		symbol: 'C',
		atomnummer: '6',
		tilstand: 'gass'
	};

	let grunnstoff4 = {
		navn: 'Fluor',
		symbol: 'H',
		atomnummer: '9',
		tilstand: 'gass'
	};

	let grunnstoff5 = {
		navn: 'Helium',
		symbol: 'He',
		atomnummer: '2',
		tilstand: 'gass'
	};

	let grunnstoffer = [grunnstoff1, grunnstoff2, grunnstoff3, grunnstoff4, grunnstoff5];
</script>

<!-- <table border=1>
	<tr
		><th>Atomnummer </th>
		<th>Symbol</th>
		<th>Navn</th>
		<th>Tilstand</th></tr
	>
	{#each grunnstoffer as stoff}
		<tr>
			<td>{stoff.atomnummer}</td>
			<td>{stoff.symbol}</td>
			<td>{stoff.navn}</td>
			<td>{stoff.tilstand}</td>
		</tr>
	{/each}
</table> -->

{#each grunnstoffer as stoff}
	<h1 style="color: blue">Grunnstoff: {stoff.navn}</h1>
	<p>Kjemisk symbol: {stoff.symbol}</p>
	<p>Atomnummer: {stoff.atomnummer}</p>
	<p>Tilstand: {stoff.tilstand}</p>
{/each}
