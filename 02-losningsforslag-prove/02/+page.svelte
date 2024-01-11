<script>
	let folelse = 5;

	//funksjon til oppgave C
	const folelseOpp = () => {
		if (folelse < 10) {
			folelse++;
		}
	};
	const folelseNed = () => {
		if (folelse > 0) {
			folelse--;
		}
	};
</script>

<h3>Hvordan føler du deg i dag?</h3>
0<input type="range" min="0" max="10" bind:value={folelse} />10

<p>
	{#if folelse < 3}
		Enten så går det bra, eller så går det over.
	{:else if folelse > 7}
		Du har en strålende dag!!
	{:else}
		En helt middels dag er deilig innimellom
	{/if}
</p>
<button on:click={folelseNed}>👎</button>
<button on:click={folelseOpp}>👍</button>
