<div>
    <div class="flag-wappen">
        <Flag
            src={FlevolandFlag}
            name="Flevoland"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Flevoland"
            type="Wappen"
        />
    </div>
    <!-- <img src={FlevolandSVG} alt=""> -->
     <section>
        <p>
            Flevoland ist die jüngste Provinz und
            entstand durch die Trockenlegung großer
            Teile des Ijsselmeers, was im Westen der neuen Provinz liegt.
            Im Jahre 1967 wurde Lelystad die offizielle Hauptstadt.
        </p>
     </section>
</div>
<script>
    import Wappen from "$lib/provinces/flevoland/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import FlevolandSVG from "$lib/provinces/flevoland/flevoland.svg"
    import FlevolandFlag from "$lib/provinces/flevoland/flag.svg"
</script>