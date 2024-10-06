<div class="groningen-container">
    <div class="flag-wappen">
        <Flag
            src={GroningenFlag}
            name="Groningen"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Groningen"
            type="Wappen"
        />
    </div>
    <section>
        <p>
            Groningen hat eine gemeinsame Grenze
            mit Niedersachsen in Deutschland und die
            Hauptstadt ist Groningen.
        </p>
    </section>
    <section class="extra">
        <div>
            <h2>Erdgasförderung</h2>
            <p>
                Das Groninger Gasfeld, Europas größtes Erdgasvorkommen,
                ist etwa 875km<sup>2</sup> groß und wurde 1959 entdeckt.
                In den Niederlanden waren 93% der Bevölkerung von dem Gas abhängig.
                Ebendfalls durch den Export aus den Niederlanden,
                spielte es eine wichtige Rolle für die dortige Wirtschaft.
                Seit 1963 wird Erdgas aus der Quelle gewonnen und bis 2022 wurden etwa 80% der
                Quelle von NAM (einer Gasförderungs-Firma) geborgen.
                Heute ist das Gasfeld geschlossen.
            </p>
        </div>
        <img src={gasfeldImg} alt="aaa">
    </section>
</div>

<style>
    .groningen-container {
        width: 100%;
        padding: 0 2rem 0 0;
    }

    h2 {
        margin: 0 0 1rem 0;
        font-size: 2.5rem;
    }

    section {
        margin-bottom: 1rem;
    }

    /* .data {
        display: flex;
        justify-content: space-between;
    } */

    .extra {
        display: grid;
        grid-template-columns: 1fr 1fr;
        object-fit: cover;
    }

    .extra div {
        padding: 0 1rem 0 0;
    }

    .extra h2 {
        font-size: 2rem;
    }

    .extra p {
        font-size: 1.5rem;
    }
    
    @media (min-height: 1500px) {
        .extra p {
            font-size: 1.8rem;
        }
    }
</style>

<script>
    import Wappen from "$lib/provinces/groningen/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import gasfeldImg from "$lib/images/gas-groningen.png"
    import GroningenSVG from "$lib/provinces/groningen/groningen.svg"
    import GroningenFlag from "$lib/provinces/groningen/flag.png"
</script>