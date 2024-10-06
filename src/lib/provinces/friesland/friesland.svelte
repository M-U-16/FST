<div>
    <div class="flag-wappen">
        <Flag
            src={FrieslandFlag}
            type="Flagge"
            name="Friesland"
        />
        <Flag
            src={Wappen}
            type="Wappen"
            name="Friesland"
        />
    </div>
    <section>
        <p>
            Friesland ist eine der Nördlichen
            Provinzen und ist die einzige in der
            es eine zweite Amtssptrache, das Friesische, gibt.
            Friesisch wird zu Teilen auch in Deutschland gesprochen.
            Zwischen dem Friesischen und Niederländischen gibt es große
            unterschiede und wenig Gemeinsamkeiten.
        </p>
    </section>
    <!-- <img src={FrieslandSVG} alt=""> -->
</div>

<script>
    import Wappen from "$lib/provinces/friesland/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import FrieslandSVG from "$lib/provinces/friesland/friesland.svg"
    import FrieslandFlag from "$lib/provinces/friesland/flag.png"
</script>