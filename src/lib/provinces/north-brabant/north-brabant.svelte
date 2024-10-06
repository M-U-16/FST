<div>
    <div class="flag-wappen">
        <Flag
            src={NorthBrabantFlag}
            name="Nordbrabant"
            type="Flagge"
        />
        <Flag
            src={Wappen}
            name="Nordbrabant"
            type="Wappen"
        />
    </div>
    <section>
        <p>
            Sowohl in den Niederlanden,
            als auch in Belgien gibt es ein „Brabant“.
            In den Niederlanden heißt die Provinz Noord-Brabant. Die Trennung erfolgte damals aufgrund der unterschiedlichen Religionszugehörigkeiten in Nord und Süd. Während die Belgier Katholiken waren waren die Niederländer Protestanten. Noord-Brabant liegt im Süden der Niederlande.
            Die Provinzhauptstadt ist Eindhoven.
        </p>
    </section>
    <!-- <img src={NorthBrabantSVG} alt=""> -->
</div>

<script>
    import Wappen from "$lib/provinces/north-brabant/wappen.svg"
    import Flag from "$lib/components/Flag.svelte"
    import NorthBrabantSVG from "$lib/provinces/north-brabant/north-brabant.svg"
    import NorthBrabantFlag from "$lib/provinces/north-brabant/flag.svg"
</script>