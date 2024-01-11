<script>
	// funksjon etter oppgave A
	const hilsA = (navn) => {
		return 'Hei på deg, ' + navn;
	};

	//funksjon etter oppgave B
	const hilsB = (navn) => {
		return 'Hei på deg, ' + navn + '. Navnet ditt består av ' + navn.length + ' bokstaver.';
	};

	//funksjon etter oppgave C
	const hilsC = (navn) => {
		if (navn.length > 8) {
			return (
				'Hei på deg, ' + navn + '. Navnet ditt består av ' + navn.length + ' bokstaver og er langt.'
			);
		} else if (navn.length <= 3) {
			return (
				'Hei på deg, ' + navn + '. Navnet ditt består av ' + navn.length + ' bokstaver og er kort.'
			);
		} else {
			return (
				'Hei på deg, ' +
				navn +
				'. Navnet ditt består av ' +
				navn.length +
				' bokstaver og er middels langt.'
			);
		}
	};

	// funksjon etter oppgave D. Det eneste som er endret fra C er at jeg
	// har lagt til if-setning dersom lengden av navnet er mindre enn
	const hilsD = (navn) => {
		if (navn.length > 8) {
			return (
				'Hei på deg, ' + navn + '. Navnet ditt består av ' + navn.length + ' bokstaver og er langt.'
			);
		} else if (navn.length < 1) {
			return '';
		} else if (navn.length <= 3) {
			return (
				'Hei på deg, ' + navn + '. Navnet ditt består av ' + navn.length + ' bokstaver og er kort.'
			);
		} else {
			return (
				'Hei på deg, ' +
				navn +
				'. Navnet ditt består av ' +
				navn.length +
				' bokstaver og er middels langt.'
			);
		}
	};

	let inputNavn = '';
</script>

<h1>Oppgave a)</h1>
<h2>{hilsA('Petter')}</h2>
<!-- Linja over burde være i h1-element ifølge oppgaveteksten, men 
for å skille tydeligere mellom oppgavene valgte jeg h2-->

<h1>Oppgave b)</h1>
<p>{hilsB('Petter')}</p>

<h1>Oppgave c)</h1>
<p>{hilsC('Petter')}</p>

<h1>Oppgave d)</h1>
<input type="text" bind:value={inputNavn} />
<p>{hilsD(inputNavn)}</p>
