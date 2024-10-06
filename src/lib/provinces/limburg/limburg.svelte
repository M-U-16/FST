<div class="limburg-container">
    <div class="flag-wappen">
        <Flag
            src={LimburgFlag}
            name="Limburg"
            type="Flaggen"
        />
        <Flag
            src={Wappen}
            name="Limburg"
            type="Wappen"
        />
    </div>
    <!-- <img src={LimburgSVG} alt=""> -->
    <section>
        <p>
            Limburg liegt ganz im Südosten der Niederlande, mit einer
            langgezogenen Grenze zu Deutschland (NRW) und
            ist besonders im Vergleich zu allen anderen Provinzen,
            denn zwischen den Limburgern und dem Rest der Niederlande
            besteht ein fortlaufende Außeinandersetung. Was sich durch
            belächeln und veräppeln der anderen Partei äußert.
            Ein Grund ist der Unterschied in Religion, denn Limburg
            ist als Ausnahme zum Rest der Niederlande stark Katholisch
            geprägt. Außerdem fühlen sie sich besonders Deutschland nah,
            wodurch der gesprochene Dialekt viele deutsche Begriffe verwendet.
        </p>
    </section>
</div>

<script>
    import Wappen from "$lib/provinces/limburg/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import LimburgSVG from "$lib/provinces/limburg/limburg.svg"
    import LimburgFlag from "$lib/provinces/limburg/flag.svg"
</script>