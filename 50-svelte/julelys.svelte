<script>
    let lys1 = false;
    let lys2 = false;
    let lys3 = false;
    let lys4 = false;
</script>

<main>
    <div class="lysestake">
        <div>
            {#if lys1}
                <img src="lys-tent.png" alt="Tent adventslys" class="lys" />
            {:else}
                <img
                    src="lys-slukket.png"
                    alt="Slukket adventslys"
                    class="lys"
                />
            {/if}
            <br />
            Tent: <input type="checkbox" bind:checked={lys1} />
        </div>
        <div>
            {#if lys2}
                <img src="lys-tent.png" alt="Tent adventslys" class="lys" />
            {:else}
                <img
                    src="lys-slukket.png"
                    alt="Slukket adventslys"
                    class="lys"
                />
            {/if}
            <br />
            Tent: <input type="checkbox" bind:checked={lys2} />
        </div>
        <div>
            {#if lys3}
                <img src="lys-tent.png" alt="Tent adventslys" class="lys" />
            {:else}
                <img
                    src="lys-slukket.png"
                    alt="Slukket adventslys"
                    class="lys"
                />
            {/if}
            <br />
            Tent: <input type="checkbox" bind:checked={lys3} />
        </div>
        <div>
            {#if lys4}
                <img src="lys-tent.png" alt="Tent adventslys" class="lys" />
            {:else}
                <img
                    src="lys-slukket.png"
                    alt="Slukket adventslys"
                    class="lys"
                />
            {/if}
            <br />
            Tent: <input type="checkbox" bind:checked={lys4} />
        </div>
    </div>
</main>

<style>
    :global(html) {
        background: #136178;
        background-image: url("julekule.png");
        /* background-size: cover; */
        background-position: center center;
        background-size: contain;
        background-repeat: no-repeat;
    }
    main {
        width: 95svw;
        color: white;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    }
    div.lysestake {
        display: flex;
        align-items: flex-end;
        justify-content: center;
        width: 100%;
    }
    div.lysestake div {
        text-align: center;
    }
    img.lys {
        width: 15vw;
    }
</style>
