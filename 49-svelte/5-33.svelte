<script>
	let saturn = 'Saturn';
	let jorda = 'Jorda';
	let uranus = 'Uranus';
	let merkur = 'Merkur';
	let mars = 'Mars';
	let g_jorda = 9.81;
	let g_mars = 3.71;
	let g_saturn = 10.4;
	let g_uranus = 8.87;
	let g_merkur = 3.7;
	let masse = 75;
	let planet = '';
</script>

<h1>Tyngde på en fremmed planet</h1>

<p>Skriv inn massen din: <input type="number" bind:value={masse} /> kg.</p>
<p>Hvilken planet er du på? <input type="text" bind:value={planet} /></p>
{#if planet != saturn && planet != merkur && planet != mars && planet != uranus && planet != jorda}
	<p>Vi kjenner ikke til denne planeten.</p>
{:else if planet == saturn}
	<p>På {planet} er tyngden din {(g_saturn * masse).toFixed(1)} N.</p>
{:else if planet == jorda}
	<p>På {planet} er tyngden din {(g_jorda * masse).toFixed(1)} N.</p>
{:else if planet == uranus}
	<p>På {planet} er tyngden din {(g_uranus * masse).toFixed(1)} N.</p>
{:else if planet == merkur}
	<p>På {planet} er tyngden din {(g_merkur * masse).toFixed(1)} N.</p>
{:else if planet == mars}
	<p>På {planet} er tyngden din {(g_mars * masse).toFixed(1)} N.</p>
{/if}


<!---------------------->
<h1>ALTERNATIV LØSNING MED OJBEKTER</h1>
<!---------------------->

<script>
	let planeter = [
		{
			navn: 'Saturn',
			tyngdeakselerasjon: 10.4
		},
		{
			navn: 'Jorda',
			tyngdeakselerasjon: 9.81
		},
		{
			navn: 'Uranus',
			tyngdeakselerasjon: 8.87
		},
		{
			navn: 'Merkur',
			tyngdeakselerasjon: 3.7
		},
		{
			navn: 'Mars',
			tyngdeakselerasjon: 3.71
		}
	];
	let masse = 75;
	let planet = '';
</script>

<h1>Tyngde på en fremmed planet</h1>

<p>Skriv inn massen din: <input type="number" bind:value={masse} /> kg.</p>
<p>Hvilken planet er du på? <input type="text" bind:value={planet} /></p>
{#if planeter.find((o) => o.navn === planet)}
	På {planeter.find((o) => o.navn === planet).navn} er tyngden din {planeter.find(
		(o) => o.navn === planet
	).tyngdeakselerasjon * masse} N.
{:else}
	Vi kjenner ikke til denne planeten.
{/if}
