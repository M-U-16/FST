<div>
    <div class="flag-wappen">
        <Flag
            src={DrentheFlag}
            type="Flagge"
            name="Drenthe"
        />
        <Flag
            src={Wappen}
            type="Wappen"
            name="Drenthe"
        />
    </div>
    <section>
        <p>
            Drenthe liegt im Nordosten der Niederlande
            direkt an Niedersachsen. Die Provinz ist eher
            ländlich geprägt und ihre Hauptstadt ist Assen.
        </p>
    </section>
</div>

<script>
    import Wappen from "$lib/provinces/drenthe/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import DrentheFlag from "$lib/provinces/drenthe/flag.png"
</script>