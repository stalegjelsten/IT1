<script>
	let frukt1 = {
		navn: '🍑 Pasjonsfukt',
		pris: 43
	};
	let frukt2 = {
		navn: '🥭 Mango',
		pris: 32
	};
	let frukt3 = {
		navn: '🍍 Ananas',
		pris: 18
	};
	frukt2.pris = 35;
</script>

<p>{frukt1.navn} koster {frukt1.pris}</p>
<p>{frukt2.navn} koster {frukt2.pris}</p>
<p>{frukt3.navn} koster {frukt3.pris}</p>

<style>
	p {
		font-size: 200%;
	}
</style>
