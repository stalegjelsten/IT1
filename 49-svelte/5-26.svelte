<script>
    let pin = 1234;
    let saldo = 2000;
    let inntastet_pin;
    let inntastet_saldo;
</script>

<h3>Velkommen til Svelte minibank, Iben!</h3>
<div>
    <label for="pin">Skriv inn pin koden din</label><br />
    <input type="number" name="" id="pin" bind:value={inntastet_pin} />
</div>
<div>
    <label for="saldo">Hvor mye vil du ta ut?</label><br /><input
        type="number"
        name=""
        id="saldo"
    /> kr
</div>

{#if pin === inntastet_pin && inntastet_saldo <= saldo}
    <p style="color:green;">
        Transaksjonen er vellykket. Din nye saldo er: {saldo - inntastet_saldo} kr.
        Takk for besøket.
    </p>
{/if}
