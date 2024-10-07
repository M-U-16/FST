<div class="container-karte">
    <div class="map-container">
        <div style="position:absolute;width:50%;text-align:start;top:3rem;">
            <h1 class="map-heading">Die Provinzen der Niederlande</h1>
        </div>
        <TouchButton mapIsActive={province} reset={resetProvince}/>
        <Map
            on:mapClick={toggleProvince}
            province={province}
        />
    </div>
    <div class="info-container">
        <div class="einwohner-chart">
            <!-- <h1 class="info-heading">
                {#if province == ""}
                Einwohner der Niederlande in den Provinzen
                {:else}
                {data[province].name}
                {/if}
            </h1> -->
            <EinwohnerChart province={province} />
        </div>
        
        <div class="info-content">
            {#if province === "groningen"}
            <Groningen/>
            {:else if province === "drenthe"}
            <Drenthe />
            {:else if province === "flevoland"}
            <Flevoland />
            {:else if province === "overijssel"}
            <Overijssel/>
            {:else if province === "limburg"}
            <Limburg />
            {:else if province === "friesland"}
            <Friesland/>
            {:else if province === "zeeland"}
            <Zeeland/>
            {:else if province === "gelderland"}
            <Gelderland />
            {:else if province === "utrecht"}
            <Utrecht />
            {:else if province === "northbrabant"}
            <NorthBrabant />
            {:else if province === "southholland"}
            <SouthHolland />
            {:else if province === "northholland"}
            <NorthHolland />
            {/if}
            
        </div>
    </div>
</div>

<style>
    .container-karte {
        width: 100%;
        height: 100%;
        position: relative;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: subgrid;
    }
    
    .map-container {
        width: 100%;
        height: 100%;
        padding: 2rem;
        position: relative;
        background-color: rgba(255, 0, 0, 0);
    }

    .info-container {
        width: 100%;
        display: grid;
        grid-template-rows: 1fr 1fr;
        overflow: hidden;
    }
    
    .info-content {
        overflow-y: auto;
    }

    .einwohner-chart {
        position: relative;
    }

    .info-heading {
        top: 0;
        font-size: 2rem;
        padding: 0.2rem 0;
        position: absolute;
        background-color: white;
    }

    .map-heading {
        font-size: 2rem;
    }

    @media (min-width: 2000px) {
        .map-heading {
            font-size: 4rem;
        }
        .info-heading {
            font-size: 3rem;
        }
    }
</style>

<script>
    import Map from "$lib/maps/map-names.svelte"
    import Groningen from "$lib/provinces/groningen/groningen.svelte"
    import Gelderland from "$lib/provinces/gelderland/gelderland.svelte"
    import Limburg from "$lib/provinces/limburg/limburg.svelte"
    import Drenthe from "$lib/provinces/drenthe/drenthe.svelte"
    import Overijssel from "$lib/provinces/overijssel/overijssel.svelte"
    import Friesland from "$lib/provinces/friesland/friesland.svelte"
    import Zeeland from "$lib/provinces/zeeland/zeeland.svelte"
    import Utrecht from "$lib/provinces/utrecht/utrecht.svelte"
    import EinwohnerChart from "$lib/components/EinwohnerChart.svelte"
    import NorthHolland from "$lib/provinces/north-holland/north-holland.svelte"
    import SouthHolland from "$lib/provinces/south-holland/south-holland.svelte"
    import NorthBrabant from "$lib/provinces/north-brabant/north-brabant.svelte"
    import Flevoland from "../../lib/provinces/flevoland/flevoland.svelte";
    import data from "$lib/provinces.json"
    import TouchButton from "../../lib/components/TouchButton.svelte";
    let provinceSvg
    let province = ""
    let sidepanelActive = false

    function toggleProvince(event) {
        province = event.detail.key
    }

    function resetProvince() {
        province = ""
    }
</script>