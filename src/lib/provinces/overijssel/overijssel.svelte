<div>
    <div class="flag-wappen">
        <Flag
            src={OverijsselFlag}
            name="Overijssel"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Overijssel"
            type="Wappen"
        />
    </div>
    <section>
        <p>
            Die Provinz Overijssel hat gemeinsame Grenzen mit Niedersachsen und Nordrhein-Westfalen.
            Die Provinzhauptstadt ist Zwolle.
            Overijssel ist geprägt durch Landwirtschaftliche Nutzung und Wälder.
        </p>
    </section>
    <!-- <img src={OverijsselSVG} alt=""> -->
</div>
<script>
    import Wappen from "$lib/provinces/overijssel/wappen.png"
    import Flag from "$lib/components/Flag.svelte";
    import OverijsselSVG from "$lib/provinces/overijssel/overijssel.svg"
    import OverijsselFlag from "$lib/provinces/overijssel/flag.png"
</script>