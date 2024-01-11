<script>
	let stemmerAp = 0;
	let stemmerH = 0;
	let stemmerFrp = 0;
	let stemmer = [];
	const stemAp = () => {
		stemmerAp += 1;
		stemmer.push('Ap');
		stemmer = stemmer;
		tellOpp();
	};
	const stemH = () => {
		stemmerH++;
		stemmer.push('H');
		stemmer = stemmer;
		tellOpp();
	};
	const stemFrp = () => {
		stemmerFrp = stemmerFrp + 1;
		stemmer.push('FrP');
		stemmer = stemmer;
		tellOpp();
	};

	let totalAntall = [0, 0, 0];
	const tellOpp = () => {
		totalAntall = [0, 0, 0];
		for (let i = 0; i < stemmer.length; i++) {
			if (stemmer[i] == 'Ap') {
				totalAntall[0]++;
			} else if (stemmer[i] == 'H') {
				totalAntall[1]++;
			} else if (stemmer[i] == 'FrP') {
				totalAntall[2]++;
			}
			totalAntall = totalAntall;
		}
	};
</script>

<h1>Stortingsvalget 2025</h1>
<p>Stem på et parti! 👇</p>
<button on:click={stemAp}>Ap</button>
<button on:click={stemH}>H</button>
<button on:click={stemFrp}>FrP</button>
<p>Stemmer: {stemmer.join(', ')}</p>
<table>
	<tr>
		<th>Parti</th>
		<th>Stemmer</th>
	</tr>
	<tr>
		<td>Ap 🌹</td>
		<td>{stemmerAp}</td>
	</tr>
	<tr>
		<td>H 🔵</td>
		<td>{stemmerH}</td>
	</tr>
	<tr>
		<td>FrP 🍎</td>
		<td>{stemmerFrp}</td>
	</tr>
</table>

{totalAntall}

<style>
	table {
		margin-top: 1rem;
		padding: 0.5rem;
		text-align: center;
		border: 1px solid black;
	}
</style>
