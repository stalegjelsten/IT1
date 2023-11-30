<script>
	let radius = 5;
	$: areal = radius ** 2 * Math.PI;
</script>

<h1>Areal av sirkel</h1>
<label for="radius ">radius: </label>
<input type="number" id="radius" bind:value={radius} />
<p>arealet er {(radius ** 2 * Math.PI).toFixed(2)} cm<sup>2</sup></p>

<p>arealet er {areal} cm<sup>2</sup></p>
