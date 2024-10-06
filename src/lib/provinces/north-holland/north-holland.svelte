<div>
    <div class="flag-wappen">
        <Flag
            src={NorthHollandFlag}
            name="Nordholland"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Nordholland"
            type="Wappen"
        />
    </div>
    
    <section>
        <p>
            Nordholland ist die Provinz zwischen dem Ijsselmeer und der Nordsee,
            die zu großen Teilen aus trockengelegten Gebieten,
            sogenannten Poldern besteht.
            Noord-Holland gehört zu den Nördlichsten drei Provinzen der Niederlande.
            Die Hauptstadt ist Haarlem.
        </p>
    </section>
    <!-- <img src={NorthHollandSVG} alt=""> -->
</div>

<script>
    import Wappen from "$lib/provinces/north-holland/wappen.svg"
    import Flag from "$lib/components/Flag.svelte";
    import NorthHollandSVG from "$lib/provinces/north-holland/north-holland.svg"
    import NorthHollandFlag from "$lib/provinces/north-holland/flag.svg"
</script>