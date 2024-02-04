<script>
	let oppgaveliste = [];
	let nyOppgave = '';
	import { browser } from '$app/environment';

	const gjorTekstTilListe = () => {
		oppgaveliste = localStorage.oppgaveliste.split(',');
		oppgaveliste = oppgaveliste.slice(0, oppgaveliste.length - 1);
	};

	const leggTilListe = () => {
		localStorage.oppgaveliste += nyOppgave + ',';
		gjorTekstTilListe();
	};

	const slettListe = () => {
		localStorage.oppgaveliste = '';
		gjorTekstTilListe();
	};

	if (browser) {
		gjorTekstTilListe();
	}
</script>

<input type="text" bind:value={nyOppgave} /> <button on:click={leggTilListe}>Legg til</button>

<ul>
	{#each oppgaveliste as husketing}
		<li>{husketing}</li>
	{/each}
</ul>

<button on:click={slettListe}>Slett alt</button>

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
