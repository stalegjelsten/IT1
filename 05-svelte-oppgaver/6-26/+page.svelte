<script>
	import { browser } from '$app/environment';
	let poeng = 0;
	let tidSisteTrykk = null;
	if (browser) {
		if (localStorage.hasOwnProperty('poeng')) {
			poeng = localStorage.poeng;
		} else {
			localStorage.poeng = 0;
		}
	}
	const leggTilPoeng = () => {
		const tidenNaa = new Date();
		if ((tidSisteTrykk && tidenNaa - tidSisteTrykk > 30000) || !tidSisteTrykk) {
			poeng = Number(localStorage.poeng) + 1;
			localStorage.poeng = poeng;
			tidSisteTrykk = new Date();
		}
	};
</script>

<h1><span>🐄</span>-klikkeren</h1>
<p>Du har klikket på kua {poeng} ganger</p>
<button on:click={leggTilPoeng}> 🐮 </button>

<style>
	h1 {
		font-size: 200%;
	}
	h1 > span {
		font-size: 150%;
	}
	p {
		font-size: 150%;
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
		font-size: 400%;
	}
</style>
