<script>
	const APInokkel = 'N1qjpFZ0Xs79ivyeGB1HpwbhACCq9Zu8';
	let videoObjekt = null;
	let laster = false;
	let sokeTekst = '';
	let videoBredde = 720;
	$: videoHoyde = Math.floor((videoBredde * 9) / 16);

	let gif = '';
	let gifVenstreMarg = videoBredde - 150;
	let gifToppMarg = 0;
	let gifSkalering = 1;

	const hentWebkamera = async () => {
		laster = true;
		const stream = await navigator.mediaDevices.getUserMedia({
			video: { width: videoBredde, height: videoHoyde }
		});
		videoObjekt.srcObject = stream;
		videoObjekt.play();
		laster = false;
	};

	const hentGif = async () => {
		const offset = Math.ceil(Math.random() * 1);
		const sporring =
			'https://api.giphy.com/v1/gifs/search?api_key=' +
			APInokkel +
			'&q=' +
			encodeURI(sokeTekst) +
			'&limit=1&offset=' +
			offset;
		if (sokeTekst == '') {
			gif = '';
		}
		const respons = await fetch(sporring);
		const resultat = await respons.json();
		gif = await resultat.data[0].images.original.url;
	};
</script>

{#if laster}
	<h1>Laster webkamera...</h1>
{/if}
<!-- svelte-ignore a11y-media-has-caption -->
<video bind:this={videoObjekt} />
<img
	src={gif}
	style="position: absolute; left: {gifVenstreMarg}px; top: {gifToppMarg}px; transform: scale({gifSkalering});"
/>
<p>
	Bredde: {videoBredde} <br />
	<input
		type="range"
		name="videoBredde"
		id="videoBredde"
		min="320"
		max="1920"
		step="10"
		bind:value={videoBredde}
	/>
</p>
<p>Høyde: {videoHoyde}</p>
<p>
	<button on:click={hentWebkamera}>Vis webkamera</button>
</p>
<p>
	<input type="text" bind:value={sokeTekst} placeholder="Giphy-søk" /> <br />
	<button on:click={hentGif}>Hent GIF</button>
</p>
<p>
	x-posisjon: {gifVenstreMarg}<br />
	<input
		type="range"
		name="venstreMarg"
		id="venstreMarg"
		min="0"
		max={videoBredde}
		step="10"
		bind:value={gifVenstreMarg}
	/>
</p>
<p>
	y-posisjon: {gifToppMarg}<br />
	<input
		type="range"
		name="toppMarg"
		id="toppMarg"
		min="0"
		max={videoHoyde}
		step="10"
		bind:value={gifToppMarg}
	/>
</p>
<input
	type="range"
	name="gifSkalering"
	id="gifSkalering"
	bind:value={gifSkalering}
	min="0.5"
	max="5"
	step="0.1"
/>
