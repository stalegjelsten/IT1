<script>
	///////////////////////
	// oppgave 2a
	///////////////////////
	const lagListe = (n) => {
		let liste = [];
		for (let i = 0; i <= n; i++) {
			liste.push(i);
		}
		return liste;
	};

	///////////////////////
	// Oppgave 2b
	///////////////////////
	const firerPotens = (n) => {
		let svar = [];
		for (let i = 0; i <= n; i++) {
			svar.push(4 ** i);
		}
		return svar;
	};

	///////////////////////
	// Oppgave 2e
	///////////////////////
	const sumAvFirerPotenser = (n) => {
		let svar = [];
		let sum = 0;
		for (let i = 0; i <= n; i++) {
			const potens = 4 ** i;
			sum += potens;
			svar.push(sum);
		}
		return svar;
	};
</script>

<h3>Oppgave 2a: Liste over tall opp til <em>n</em></h3>
<p>
	<em
		>Det er ikke nødvendig å skrive ut noe fra funksjonen. Linjen nedenfor er kun ment for å gjøre
		det enklere å forstå løsningsforslaget.</em
	>
</p>
<p>Liste over tall fra 0 opp til 4: {lagListe(4).join(", ")}</p>

<h3>Oppgave 2b: Liste over firerpotenser</h3>
<p>
	<em
		>Det er ikke nødvendig å skrive ut noe fra funksjonen. Linjen nedenfor er kun ment for å gjøre
		det enklere å forstå løsningsforslaget.</em
	>
</p>
<p>Liste over tall fra 4<sup>0</sup> til 4<sup>4</sup>: {firerPotens(4).join(", ")}</p>

<h3>Oppgave 2c: Forklare tallfølge</h3>
<p>Hvert tall i tallfølgen er en firerpotens, pluss summen av alle de foregående firerpotensene.</p>
<p>
	For eksempel er er det tredje leddet i følgen 21 siden 4<sup>0</sup> + 4<sup>1</sup> + 4<sup
		>2</sup
	> = 1 + 4 + 16 = 21.
</p>

<h3>Oppgave 2d: Pseudokode for summen til firerpotensener</h3>

<pre>
<code>
Hent inn et tall n fra brukeren
Opprett en tom liste
Sett sum til 0
For hvert tall fra 0 til n:
  Legg til 4^tall til sum
  Legg til sum i slutten av lista
</code>
</pre>

<h3>Oppgave 2e: Sum av firerpotenser</h3>
<p>
	<em
		>Det er ikke nødvendig å skrive ut noe fra funksjonen. Linjen nedenfor er kun ment for å gjøre
		det enklere å forstå løsningsforslaget.</em
	>
</p>
<p>Liste over de syv første summene av syverpotenser: {sumAvFirerPotenser(7).join(", ")}</p>
