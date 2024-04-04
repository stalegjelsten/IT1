<script>
    let tall = 1;

    // funksjon som deler tallet x på alle heltall <= x
    const deleHeltall = (x) => {
        let svar = []; // oppretter tomt array med svarene
        for (let nevner = 1; nevner <= x; nevner++) {
            const brok = x / nevner; // regner ut brøken x / nevner
            svar.push(x / nevner); //
        }
        return svar;
    };

    // funksjon som bestemmer om et tall er primtall ved å telle opp antall heltallsfaktorer
    const bestemOmPrimtall = (x) => {
        const svar = deleHeltall(x); // bruker funksjonen for å hente et array med x delt hvert heltall <= x
        let antallFaktorer = 0;
        for (let i = 0; i < x; i++) {
            // for løkke som går gjennom array svar
            if (svar[i] == Math.round(svar[i])) {
                antallFaktorer += 1; // hvis elementet svar[i] er lik det samme avrundede elementet, så må elementet være et heltall
            }
        }
        if (antallFaktorer > 2) {
            return false;
        } else {
            return true;
        }
    };
</script>

<h2>Oppgave 3c</h2>
<p>Her er 10 delt på alle heltall ≤ 10</p>
<ul>
    {#each deleHeltall(10) as kvotient, i}
        <li>10 ÷ {i + 1} = {kvotient}</li>
    {/each}
</ul>

<h2>Oppgave 3d</h2>
<input type="number" bind:value={tall} />
<p>
    {#if bestemOmPrimtall(tall)}
        {tall} er primtall.
    {:else}
        {tall} er ikke primtall.
    {/if}
</p>

<h3>Oppgave 3e</h3>
<p>
    Vi trenger egentlig ikke teste alle mulige heltall mindre enn <em>x</em> for
    å sjekke om <em>x</em> er primtall. Vi trenger egentlig kun å sjekke opp til
    og med kvadratroten av <em>x</em> (√<em>x</em>). I tillegg trenger vi ikke
    teste partall over 2, siden hvis <em>x</em> kan deles på et partall større
    enn 2, så kan det også alltid deles på 2. Vi er jo egentlig ikke interessert
    i å telle hvor mange faktorer <em>x</em> har, vi er kun interessert i om det
    er mer enn 2 eller ikke.
</p>
