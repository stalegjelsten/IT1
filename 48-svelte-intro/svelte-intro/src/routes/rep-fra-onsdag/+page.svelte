<script>
	let tall = Math.random() * 5;
	let nyttTall = tall.toFixed(2);
	let tall1 = 5;
	let tall2 = 2;
	let tekst = 'CR';
	let ord = 'fiskebolle';
</script>

<h1>Velkommen!</h1>
<p>Her kan jeg skrive en blanding av HTML og Javascriptkode.</p>
<p>Jeg bruker krøllparenteser rundt Javascriptkode: <b>{nyttTall}</b></p>

<p>{tall1 + tall2 + tekst}</p>
<p>{tekst + tall1 + tall2}</p>
<p>{tekst + (tall1 + tall2)}</p>

<p>Eksempel 1: {ord.toUpperCase()[4]}</p>
<p>Eksempel 2: {ord.split('o').join('ø')}</p>
<p>Eksempel 3: {ord.replaceAll('e', 'a')}</p>
<p>Eksempel 4: {ord.length}</p>
