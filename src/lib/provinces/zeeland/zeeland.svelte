<div>
    <div class="flag-wappen">
        <Flag
            src={ZeelandFlag}
            name="Zeeland"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Zeeland"
            type="Wappen"
        />
    </div>
    <section>
        <p>
            Die Provinz Zeeland besteht im wesentlichen aus drei Großen Inseln,
            die mit mehreren Brücken und Dämmen verbunden sind.
            Durch die Nähe zum Wasser steht die Provinz im stetigen Kampf mit dem
            Meer.
        </p>
    </section>
    <section>
        <div>
            <h1>Oosterschelde-Sturmflutwehr</h1>
            <p>
                Das Oosterschelde-Sturmflutwehr ist ein 9km langes Sperrwerk.
                In der Nacht vom 31.Januar auf dem 1.Februar 1953 gab es in
                den Niederlanden eine Flutkatastrophe, ausgelöst von einem
                Nordweststurm und einer Springflut.
                Die Niederlande bauten deshalb, sogenannte Deltawerke und das
                Oosterschelde-Sturmflutwehr ist eines der größten und bekanntesten davon.
                Bei hohen Wasserständen werden die Tore runter gefahren und
                schützen so das Land dahinter.
            </p>
        </div>
        <img src={sturmflutwehr} alt="Sturmflutwehr">
    </section>
    <section>
        <img src={leuchtturm} alt="Leuchtturm">
        <div>
            <h1>Leuchtturm Westerlichttoren in Haamstede</h1>
            <p>
                Der Leuchtturm verdankt seine Bekanntheit der
                Abbildung auf dem 250-Gulden-Schein. Gulden waren
                die Währung in der Niederlande, bevor sie am 1. Januar 2002
                durch den Euro abgelöst wurde. 
            </p>
        </div>
    </section>
</div>

<style>
    section {
        display: grid;
        grid-template-columns: 1fr 1fr;
    }

    section img {
        width: 100%;
    }

    section p {
        font-size: 1.2rem;
    }

    @media (min-height: 1500px) {
        section p {
            font-size: 2rem;
        }
    }
</style>

<script>
    import Wappen from "$lib/provinces/zeeland/wappen.png"
    import Flag from "$lib/components/Flag.svelte"
    import leuchtturm from "$lib/provinces/zeeland/leuchtturm.jpg"
    import sturmflutwehr from "$lib/provinces/zeeland/sturmflutwehr.png"
    import ZeelandFlag from "$lib/provinces/zeeland/flag.svg"
    import ZeelandSVG from "$lib/provinces/zeeland/zeeland.svg"
</script>