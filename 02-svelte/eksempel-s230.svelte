<script>
	let elever = [];
	let navn = '';
	const registrerElev = () => {
		elever.push(navn);
		elever = elever;
		navn = '';
	};
</script>

<input type="text" bind:value={navn} />
<button on:click={registrerElev}>Registrer oppmøte</button>
<h1>Elever som har lappen
</h1>
<p>{elever.join(" 🎓 ")}</p>