<!-- oppgave 5.26 -->
<script>
    let pinKode = 1111;
    let riktig_pin = 1234;
    let uttak = 0;
    let saldo = 2000;
    let navn = "AlexAnder";
</script>

<h1>Velkommen til svelte minibank, {navn}!</h1>
<label for="pin">Skriv inn pin-koden: </label>
<input type="text" name="" id="pin" bind:value={pinKode} />

<br />
<label for="uttak">Skriv inn beløp: </label>
<input type="number" name="" id="uttak" bind:value={uttak} />

{#if pinKode != 1234}
    <p style="color:red;">PIN-koden er feil, {navn}!</p>
{:else if pinKode == 1234 && uttak > saldo}
    <p style="color:blue;">
        Du har ikke nok penger på konto, prøv et mindre beløp
    </p>
{:else if pinKode == 1234 && uttak <= saldo}
    <p style="color:green;">
        Transaksjonen var vellyket. Saldoen er {saldo - uttak}
    </p>
{/if}
