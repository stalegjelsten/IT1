<script>
    let a = 1;
    let b = 1;
    let c = -1;

    // Math.sign() henter fortegnet til et tall. Funksjonen returnerer 1 hvis
    // tallet er positivt, 0 hvis tallet er 0 og -1 dersom tallet er negativt
    // Her bruker jeg er "terenary operator". Dersom vilkåret Math.sign(b) >= 0
    // er sant så vil fortegnB bli lik "+". Dersom vilkåret er usant så vil
    // fortegnB bli "-"
    $: fortegnB = Math.sign(b) >= 0 ? "+" : "–";
    $: fortegnC = Math.sign(c) >= 0 ? "+" : "–";

    // Diskriminanten er den delen av andregradsformelen som er under rottegnet
    // Dersom denne er > 0 så får vi 2 løsninger. Dersom den er lik 0 så har vi
    // en løsning og dersom den er < 0 så får vi ingen reelle løsninger.
    $: diskriminant = b ** 2 - 4 * a * c;

    // Henter a og b, samt fortegnet som vi ønsker å bruke mellom -b og diskriminanten
    // i andregradsformelen. Hvis sign == 1 så velger vi løsningen med -b + sqrt(b^2-4ac),
    // dersom den er negativ så velger vi løsningen -b - sqrt(b^2-4ac)
    const losning1 = (a, b, sign) => {
        // Bruker terenary operatoren her også og sjekker om sign == 1
        const teller =
            sign == 1
                ? -b + Math.sqrt(diskriminant)
                : -b - Math.sqrt(diskriminant);
        const nevner = 2 * a;

        // Runder av svaret til 4 desimaler og returnerer det
        return Math.round(teller / nevner, 4);
    };
</script>

<h1>Andregradskalkulator</h1>
<p>Legg inn koeffisientene til andregradslikningen i feltene under.</p>

a:<input type="number" bind:value={a} size="5" /> b:
<input type="number" bind:value={b} size="5" />
c:
<input type="number" bind:value={c} size="5" />

<!--
  Nyttige tagger for å skrive matematikk.

  <sup> gir superscript eller hevet tekst
  <sub> gir subscript eller senket skrift
  <i> gir kursiv tekst. Alle variabler i matematikk skal være satt i kursiv
-->

{#if a == 0 || a == null}
    <p>
        Skriv inn en gyldig verdi for <i>a</i>. a må være et annet tall enn
        null.
    </p>
{:else}
    <p>
        Andregradslikningen
        {a}<i>x</i><sup>2</sup>
        <!-- Her velger jeg å skrive ut fortegnet foran b først, og deretter
         kun skrive ut absoluttverdien til b. På den måten slipper jeg å få +-
         rett etter hverandre -->
        {fortegnB}
        {Math.abs(b)}<i>x</i>
        {fortegnC}
        {Math.abs(c)} = 0 har
        {#if diskriminant == 0}
            en løsning: <b><i>x</i> = {-b / (2 * a)} </b>
        {:else if diskriminant > 0}
            to løsninger: <b><i>x</i><sub>1</sub> = {losning1(a, b, -1)} </b> og
            <b><i>x</i><sub>2</sub> = {losning1(a, b, 1)} </b>
        {:else}
            ingen løsninger.
        {/if}
    </p>
{/if}
