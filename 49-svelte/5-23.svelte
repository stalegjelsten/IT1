<script>
    let walks = false;
    let quacks = false;
</script>

<label for="walk">Går som en and </label>
<input type="checkbox" name="" id="walk" bind:checked={walks} />
<br />
<label for="quack">Kvekker </label>
<input type="checkbox" name="quack" id="quack" bind:checked={quacks} />

{#if walks && quacks}
    <p>Dette er en and.</p>
{/if}
