<script>
	let oppgaveliste = [];
	let nyOppgave = '';

	const leggTilListe = () => {
		oppgaveliste.push(nyOppgave);
		oppgaveliste = oppgaveliste;
	};
</script>

<input type="text" bind:value={nyOppgave} /> <button on:click={leggTilListe}>Legg til</button>

<ul>
	{#each oppgaveliste as husketing}
		<li>{husketing}</li>
	{/each}
</ul>

<style>
	input,
	ul {
		font-size: 300%;
		font-family:
			system-ui,
			-apple-system,
			BlinkMacSystemFont,
			'Segoe UI',
			Roboto,
			Oxygen,
			Ubuntu,
			Cantarell,
			'Open Sans',
			'Helvetica Neue',
			sans-serif;
	}
	button {
		font-size: 200%;
	}
</style>
