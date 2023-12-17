<script>
    let hoyde = 1.5;
</script>

<label for="hoyde">Høyde: </label>
<input type="number" id="hoyde" bind:value={hoyde} />
{#if hoyde > 3}
    <p>
        NB! Du kan ikke skrive inn en høydere høyere enn 3 meter; Kontakt
        Guinness rekordbok dersom du er høyere.
    </p>
{:else}
    <p>Du er {hoyde} m høy!</p>
{/if}
