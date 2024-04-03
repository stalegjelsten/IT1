<script>
    let figNummer = 1;
    const naturligSum = () => {
        let sum = 0;
        for (let tall = 1; tall <= 10; tall++) {
            sum += tall;
        }
        return sum;
    };

    const kvadratSum = () => {
        let sum = 0;
        for (let i = 0; i <= 10; i++) {
            sum += i ** 2;
        }
        return sum;
    };
    const antallGronne = (n) => {
        return 2 * n * n + n;
    };

    const samletGronne = (n) => {
        let sum = 0;
        for (let i = 1; i <= n; i++) {
            sum += antallGronne(i);
        }
        return sum;
    };
</script>

<h2>Oppgave 3d</h2>
<p>Summen av de ti første naturlige tallene: {naturligSum()}</p>

<h2>Oppgave 3e</h2>
<p>Summen av de 10 første kvadrattallene: {kvadratSum()}</p>

<h2>Oppgave 3f</h2>
<p>Antall øyne i figur 4: {antallGronne(4)}</p>

<h2>Oppgave 3h</h2>
<input type="number" min="1" bind:value={figNummer} />
<p>
    Det er {antallGronne(figNummer)} i figur {figNummer}, og det samlede
    antallet du trenger for å lage alle figurene er {samletGronne(figNummer)}
</p>
