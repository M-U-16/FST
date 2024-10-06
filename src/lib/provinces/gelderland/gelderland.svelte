<div>
    <div class="flag-wappen">
        <Flag
            src={GelderlandFlag}
            name="Gelderland"
            type="Flaggen"    
        />
        <Flag
            src={Wappen}
            name="Gelderland"
            type="Wappen"    
        />
    </div>
    <section>
        <p>
            Gelderland liegt im Osten der Niederlande
            mit einer gemeinsamen Grenze zum Bundesland
            Nordrhein-Westfahlen. Die Namensgebende Stadt
            für Gelderland liegt mittlerweile in Deutschland
            und die Hauptstadt ist Arnheim.
        </p>
    </section>
    <!-- <img src={GelderlandSVG} alt=""> -->
</div>

<script>
    import Wappen from "$lib/provinces/gelderland/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import GelderlandSVG from "$lib/provinces/gelderland/gelderland.svg"
    import GelderlandFlag from "$lib/provinces/gelderland/flag.svg"
</script>