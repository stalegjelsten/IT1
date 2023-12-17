<script>
    let ph = 7;
</script>

<h1>pH-skala</h1>
<input type="range" name="" id="pH-slider" min="0" max="14" bind:value={ph} />
<p>
    Når pH-en til en løsning er {ph},
    {#if ph < 7}
        er den sur <br />
        <span style="font-size:4rem;">😢</span>
    {:else if ph > 7}
        er den basisk <br />
        <span style="font-size:4rem;">😫</span>
    {:else}
        er den nøytral <br />
        <span style="font-size:4rem;">😐</span>
    {/if}
</p>
