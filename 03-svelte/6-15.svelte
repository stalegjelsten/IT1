<script>
    let sprintere = [
        { navn: "Gløer Langslet", tid: 9.5 },
        { navn: "Usain Bolt", tid: 9.58 },
        { navn: "Asafa Powell", tid: 9.74 },
    ];

    const sorterNavn = () => {
        sprintere = sprintere.sort((a, b) => a.navn.localeCompare(b.navn));
    };
    const sorterTid = () => {
        sprintere = sprintere.sort((a, b) => a.tid - b.tid);
    };
</script>

<ol>
    {#each sprintere as sprinter}
        <li>{sprinter.navn} {sprinter.tid}</li>
    {/each}
</ol>

<button on:click={sorterNavn}>Sorter navn</button>
<button on:click={sorterTid}>Sorter tid</button>
