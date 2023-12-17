<script>
    let a = 3;
    let b = 8;
    $: snitt = () => {
        return (a + b) / 2;
    };
</script>

<p>a = <input type="number" name="" id="tall1" bind:value={a} /></p>
<p>b = <input type="number" name="" id="tall2" bind:value={b} /></p>
<p>Gjennomsnitt: {snitt()}</p>
