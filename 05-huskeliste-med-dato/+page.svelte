<script>

let dato = new Date() // opppretter et nytt datoobjekt
let huskeliste = []   // tom huskeliste
let hva = "" // "hva" er teksten sin skal huskes

// lager en ny dato hvor jeg tar hensyn til tidssonen med getTimezoneOffset og
// legger til 1 time (60*60*1000). Denne datoen gjør jeg om til en tekststreng
// som jeg kun bruker de første 16 tegnene av. Dette brukes til å sette et 
// "default" tidspunkt for datovelgeren.
let naar = new Date(dato.getTime() - (dato.getTimezoneOffset() * 60000) + 60 * 60 * 1000).toISOString().slice(0,16)

// henter fram en huskeliste fra localstorage og gjør den til et objekt med
// JSON.parse()
import { browser } from '$app/environment'
if (browser) {
    if (localStorage.hasOwnProperty('huskeliste')) {
        huskeliste = JSON.parse(localStorage.huskeliste)
    }
}

// legeger til objekt i liste
const leggTilListe = () => {
    huskeliste.push({
        "hva": hva, 
        "naar": naar})

    // lagrer listen som en tekststreng til localstorage
    localStorage.huskeliste = JSON.stringify(huskeliste)

    // husker å tilordne listen til seg selv for at Svelte skal oppdatere seg
    huskeliste = huskeliste 
}

const slettObjekt = (indeks) => {
    // sletter objektet på indeksen "indeks"
    huskeliste.splice(indeks, 1)

    // lagrer listen som en tekststreng til localstorage
    localStorage.huskeliste = JSON.stringify(huskeliste)

    // husker å tilordne listen til seg selv for at Svelte skal oppdatere seg
    huskeliste = huskeliste
}

</script>

<input type="text" bind:value={hva} placeholder="Hva skal du huske?" />
<input type="datetime-local" bind:value={naar}  />
<button on:click={leggTilListe}>Legg til</button>

<ul>
    {#each huskeliste as husketing, i}
        <!-- Gjør om datofeltet til en dato igjen. Kaller med på funksjonen slettObjekt med en anonym funksjon -->
        <li>{new Date(husketing.naar).toLocaleString()}: {husketing.hva} <button on:click={() => {slettObjekt(i)}}>Slett</button></li>
    {/each}
</ul>
