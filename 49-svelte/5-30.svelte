<script>
    let src = "http://placekitten.com/200/300";
    let rotasjon = 90;
    const roter = () => {
        rotasjon += 90;
    };
</script>

<img
    {src}
    alt="en katt"
    style="transform: rotate({rotasjon}deg);"
    on:click={roter}
/>
