<div class="sidepanel{sidepanelActive?" active": ""}">
    <Close on:close={close} />
    {#if data }
        
    <div class="top">
        <div class="text">
            <h1>{data.name}</h1>
            {#if data.realName}
            <p>
                Niederländischer Name:
                <span>{data.realName}</span>
            </p>
            {/if}
            {#if data.hauptstadt}
            <p>
                Hauptstadt:
                <span>{data.hauptstadt}</span>
            </p>
            {/if}
            {#if data.population.number}
            <p>
                Einwohner:
                <span>
                    {data.population.number}
                    {data.population.percent ? `(${data.population.percent})`:""}
                </span>
            </p>
            {/if}
        </div>
        <Minimap img={province?svgs[province]:undefined} />
        <img class="flag" src={flag} alt="">
    </div>
    {/if}
    <!-- <Groningen /> -->
</div>

<style>
    .sidepanel {
        top: 0;
        right: 0;
        height: 100%;
        position: fixed;
        background-color: white;
        width: 45vw;
        padding: 2rem;
        border-left: 1px solid #7d7d7d;
        border-top: 1px solid #7d7d7d;
        box-shadow: 0px 0px 2px rgb(107, 107, 107);
        transition: opacity 0.5s ease, transform 0.8s ease;
        transform: translateX(100%);
        opacity: 0;
    }

    .active {
        transform: translate(0);
        opacity: 1;
    }

    .top {
        display: grid;
        /* justify-content: space-between; */
        align-items: center;
        justify-content: center;
        grid-template-columns: 2fr 1fr 1fr;
    }

    .top img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border: 1px solid black;
    }

    .text p {
        margin: 0;
    }
</style>

<script>
    import Groningen from "$lib/provinces/groningen/groningen.svelte";
    import Utrecht from "$lib/provinces/utrecht/utrecht.svelte";
    import Limburg from "$lib/provinces/limburg/limburg.svelte";
    import NorthBrabant from "$lib/provinces/north-brabant/north-brabant.svelte";
    import NorthHolland from "$lib/provinces/north-holland/north-holland.svelte";
    import SouthHolland from "$lib/provinces/south-holland/south-holland.svelte";
    import Friesland from "$lib/provinces/friesland/friesland.svelte";
    import Overijssel from "$lib/provinces/overijssel/overijssel.svelte";
    import Zeeland from "$lib/provinces/zeeland/zeeland.svelte";
    import Flevoland from "$lib/provinces/flevoland/flevoland.svelte";
    import Drenthe from "$lib/provinces/drenthe/drenthe.svelte";
    import Gelderland from "$lib/provinces/gelderland/gelderland.svelte";

    import DrentheSVG from "$lib/provinces/drenthe/drenthe.svg"
    import FlevolandSVG from "$lib/provinces/flevoland/flevoland.svg"
    import GelderlandSVG from "$lib/provinces/gelderland/gelderland.svg"
    import GroningenSVG from "$lib/provinces/groningen/groningen.svg"
    import LimburgSVG from "$lib/provinces/limburg/limburg.svg"
    import NorthBrabantSVG from "$lib/provinces/north-brabant/north-brabant.svg"
    import NorthHollandSVG from "$lib/provinces/north-holland/north-holland.svg"
    import SouthHollandSVG from "$lib/provinces/south-holland/south-holland.svg"
    import UtrechtSVG from "$lib/provinces/utrecht/utrecht.svg"
    import ZeelandSVG from "$lib/provinces/zeeland/zeeland.svg"
    import OverijsselSVG from "$lib/provinces/overijssel/overijssel.svg"
    import FrieslandSVG from "$lib/provinces/friesland/friesland.svg"

    const svgs = {
        drenthe: DrentheSVG,
        flevoland: FlevolandSVG,
        gelderland: GelderlandSVG,
        groningen: GroningenSVG,
        limburg: LimburgSVG,
        northbrabant: NorthBrabantSVG,
        northholland: NorthHollandSVG,
        southholland: SouthHollandSVG,
        utrecht: UtrechtSVG,
        zeeland: ZeelandSVG,
        overijssel: OverijsselSVG,
        friesland: FrieslandSVG
    }

    import DrentheFlag from "$lib/provinces/drenthe/flag.png"
    import FlevolandFlag from "$lib/provinces/flevoland/flag.svg"
    import GelderlandFlag from "$lib/provinces/gelderland/flag.svg"
    import GroningenFlag from "$lib/provinces/groningen/flag.png"
    import LimburgFlag from "$lib/provinces/limburg/flag.svg"
    import NorthBrabantFlag from "$lib/provinces/north-brabant/flag.svg"
    import NorthHollandFlag from "$lib/provinces/north-holland/flag.svg"
    import SouthHollandFlag from "$lib/provinces/south-holland/flag.png"
    import UtrechtFlag from "$lib/provinces/utrecht/flag.svg"
    import ZeelandFlag from "$lib/provinces/zeeland/flag.svg"
    import OverijsselFlag from "$lib/provinces/overijssel/flag.png"
    import FrieslandFlag from "$lib/provinces/friesland/flag.png"

    const flags = {
        drenthe: DrentheFlag,
        flevoland: FlevolandFlag,
        gelderland: GelderlandFlag,
        groningen: GroningenFlag,
        limburg: LimburgFlag,
        northbrabant: NorthBrabantFlag,
        northholland: NorthHollandFlag,
        southholland: SouthHollandFlag,
        utrecht: UtrechtFlag,
        zeeland: ZeelandFlag,
        overijssel: OverijsselFlag,
        friesland: FrieslandFlag
    }
    
    import ProvinceData from "$lib/provinces.json"
    import Minimap from "$lib/maps/Minimap.svelte"
    import Close from "$lib/components/Close.svelte";

    let data
    let flag
    export let province
    export let sidepanelActive = false
    export let close = () => {}

    $: data = ProvinceData[province]
    $: flag = flags[province]

</script>