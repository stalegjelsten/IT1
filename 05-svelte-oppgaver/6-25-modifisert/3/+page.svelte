<script>
	import { browser } from '$app/environment';
	let oppgaveliste = [];
	let nyOppgave = '';
	if (browser) {
		if (localStorage.hasOwnProperty('oppgaver')) {
			oppgaveliste = localStorage.oppgaver.split(',');
		}
	}

	const leggTilListe = () => {
		oppgaveliste.push(nyOppgave);
		localStorage.oppgaver = oppgaveliste.join(',');
		oppgaveliste = oppgaveliste;
	};

	const slettOppgaver = () => {
		oppgaveliste = [];
		localStorage.oppgaver = '';
	};
</script>

<input type="text" bind:value={nyOppgave} /> <button on:click={leggTilListe}>Legg til</button>

<ul>
	{#each oppgaveliste as husketing}
		<li>{husketing}</li>
	{/each}
</ul>
<button on:click={slettOppgaver}>Slett oppgaver!</button>

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
