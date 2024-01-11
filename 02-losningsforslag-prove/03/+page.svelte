<script>
	let titler = [
		'Å vanne blomster om kvelden',
		'I tilfell brann',
		'Den lille mannen fra Argentina',
		'De vakre dagene'
	];
	let forfattere = ['Valerie Perrin', 'Frida Andersen', 'Kristian Klausen', 'Rannveig Fern Leite'];

	//oppgave B
	titler.push('Jenta med blå stjerne');
	forfattere.push('Pam Jenoff');
</script>

<h2>Oppgave a</h2>
<p>Titler: {titler.join(', ')}</p>
<p>Forfattere: {forfattere.join(', ')}</p>

<h2>Oppgave c</h2>
<ul>
	{#each titler as tittel}
		<li>{tittel}</li>
	{/each}
</ul>

<h2>Ekstra: hvis man ønsker å kombinere arrayene for tittel og forfatter</h2>
Når du lager en<i> each</i>-blokk i Svelte så kan du skrive som <i> #each titler as tittel, i </i>.
Da vil <i>tittel</i> inneholde tittelen til boka (selve elementet i arrayen), mens <i>indeks</i> vil
inneholde indeksen til elementet.
<ul>
	{#each titler as tittel, indeks}
		<li>{tittel} av {forfattere[indeks]}</li>
	{/each}
</ul>
