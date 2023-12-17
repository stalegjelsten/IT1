<script>
    const film1Slug = "H9Z3_ifFheQ?autoplay=1";
    const film2Slug = "jaJuwKCmJbY?autoplay=1";
    const film3Slug = "jEDaVHmw7r4?autoplay=1";
    let filmSlug = "H9Z3_ifFheQ";
</script>

<main>
    <div class="videospiller">
        <iframe
            src={"https://www.youtube.com/embed/" + filmSlug}
            frameborder="0"
            width="100%"
            height="100%"
            allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
        ></iframe>
    </div>
    <div class="meny">
        <ul>
            <li
                on:click={() => {
                    filmSlug = film1Slug;
                }}
            >
                Love Actually
            </li>
            <li
                on:click={() => {
                    filmSlug = film2Slug;
                }}
            >
                Die Hard
            </li>
            <li
                on:click={() => {
                    filmSlug = film3Slug;
                }}
            >
                Home Alone
            </li>
        </ul>
    </div>
</main>

<style>
    main {
        display: flex;
        width: 97vw;
        justify-content: center;
    }
    div.videospiller {
        width: 60vw;
        aspect-ratio: 16/9;
    }
    div.meny {
        width: 20vw;
    }
</style>
