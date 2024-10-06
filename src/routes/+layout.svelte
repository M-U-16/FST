<div class="app">
    <div class="navbar">
        <div class="img-container">
            <!-- <img src={Flag} alt="flagge"> -->
            <svg>
                <rect
                    style="fill:#AF1623;"
                    width="100%"
                    height="34%"
                ></rect>
                <rect
                    style="fill:white"
                    y="33.3%"
                    width="100%"
                    height="34%"
                ></rect>
                <rect
                    style="fill:#1B448C;"
                    y="66%"
                    width="100%"
                    height="34%"
                ></rect>
            </svg>
        </div>
        <h1>Die Niederlande</h1>
    </div>
    <div class="container-layout">
        <div class="sidenav">
            <a href="/" class:active={$page.url.pathname=="/"}>
                <div class="svg-container">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 512 512"
                >
                    <path
                        d="M313.27 124.64L198.73 51.36a32 32 0 00-29.28.35L56.51 127.49A16 16 0 0048 141.63v295.8a16 16 0 0023.49 14.14l97.82-63.79a32 32 0 0129.5-.24l111.86 73a32 32 0 0029.27-.11l115.43-75.94a16 16 0 008.63-14.2V74.57a16 16 0 00-23.49-14.14l-98 63.86a32 32 0 01-29.24.35zM328 128v336M184 48v336"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="32"
                    />
                </svg>
                </div>
                <!-- <span>Karte</span> -->
            </a>
            <a href="/hymne" class:active={$page.url.pathname=="/hymne"}>
                <div class="svg-container">
                    <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 512 512"
                >
                    <path
                        d="M192 218v-6c0-14.84 10-27 24.24-30.59l174.59-46.68A20 20 0 01416 154v22"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round" stroke-width="32"
                    />
                    <path
                        d="M416 295.94v80c0 13.91-8.93 25.59-22 30l-22 8c-25.9 8.72-52-10.42-52-38h0a33.37 33.37 0 0123-32l51-18.15c13.07-4.4 22-15.94 22-29.85V58a10 10 0 00-12.6-9.61L204 102a16.48 16.48 0 00-12 16v226c0 13.91-8.93 25.6-22 30l-52 18c-13.88 4.68-22 17.22-22 32h0c0 27.58 26.52 46.55 52 38l22-8c13.07-4.4 22-16.08 22-30v-80"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="32"
                    />
                </svg>
                </div>
                <!-- <span>Hymne</span> -->
            </a>
            <a href="/famous-people" class:active={$page.url.pathname=="/famous-people"}>
                <div class="svg-container">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="0 0 512 512"
                    >
                        <path
                            d="M402 168c-2.93 40.67-33.1 72-66 72s-63.12-31.32-66-72c-3-42.31 26.37-72 66-72s69 30.46 66 72z"
                            fill="none"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="32"
                        />
                        <path
                            d="M336 304c-65.17 0-127.84 32.37-143.54 95.41-2.08 8.34 3.15 16.59 11.72 16.59h263.65c8.57 0 13.77-8.25 11.72-16.59C463.85 335.36 401.18 304 336 304z"
                            fill="none"
                            stroke-miterlimit="10"
                            stroke-width="32"
                        />
                        <path
                            d="M200 185.94c-2.34 32.48-26.72 58.06-53 58.06s-50.7-25.57-53-58.06C91.61 152.15 115.34 128 147 128s55.39 24.77 53 57.94z"
                            fill="none"
                            stroke-linecap="round" stroke-linejoin="round"
                            stroke-width="32"
                        />
                        <path
                            d="M206 306c-18.05-8.27-37.93-11.45-59-11.45-52 0-102.1 25.85-114.65 76.2-1.65 6.66 2.53 13.25 9.37 13.25H154"
                            fill="none"
                            stroke-linecap="round"
                            stroke-miterlimit="10"
                            stroke-width="32"
                        />
                    </svg>
                </div>
            </a>
        </div>
        <slot/>
    </div>
    <Controls volume={audioVolume} />
</div>

<style>
    :global(*) {
        box-sizing: border-box;
        padding: 0;
        margin: 0;
    }
    :global(:root) {
        --app-grey: #efefef;
    }

    :global(body) {
        margin: 0;
        padding: 0;
        background-color: white;
        min-height: 100vh;
        font-family: Arial, Helvetica, sans-serif;
    }

    :global(.prevent-select) {
        -webkit-user-select: none; /* Safari */
        -ms-user-select: none; /* IE 10 and IE 11 */
        user-select: none; /* Standard syntax */
    }

    .app {
        width: 100vw;
        height: 100vh;
        display: grid;
        overflow: hidden;
        grid-template-rows: 10vh 90vh;
    }

    .container-layout {
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-rows: subgrid;
        grid-template-columns: auto 1fr;
    }

    .navbar {
        height: 100%;
        width: 100%;
        display: flex;
        overflow: hidden;
        padding: 1rem;
        align-items: center;
        background-color: white;
    }

    .navbar .img-container {
        overflow: hidden;
        position: relative;
        width: 10rem;
        aspect-ratio: 2/1;
    }
    
    .navbar .img-container svg{
        /* border: 3px solid rgb(0, 0, 0); */
        width: 100%;
        height: 100%;
    }

    .navbar h1 {
        font-size: 2.5rem;
        margin-left: 0.5rem;
    }

    .sidenav {
        width: 10vw;
        height: 100%;
        max-width: 25rem;
        min-width: 10rem;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        justify-content: center;
    }

    .sidenav a {
        width: 100%;
        padding: 0rem;
        height: 10rem;
        display: flex;
        color: black;
        font-size: 2rem;
        aspect-ratio: 1/1;
        text-decoration: none;
        align-items: center;
        justify-content: center;
        border-radius: 0 5px 5px 0;
        grid-template-columns: auto 1fr;
        background-color: var(--app-grey);
        transition: background-color 0.3s ease;
    }

    .sidenav a .svg-container {
        width: 5rem;
        height: 5rem;
    }

    .sidenav a .svg-container svg {
        width: 100%;
        height: 100%;
        stroke: rgb(150, 150, 150);
        fill: none;
    }

    .sidenav a.active {
        background-color: #1B448C;
    }
    .sidenav a.active .svg-container svg {
        stroke: white;
    }
    
    :global(.flag-wappen) {
        display: flex;
    }

    /* media min-height 1500 */
    @media (min-height: 1500px) {
        :global(body) {
            font-size: 45px;
        }

        .app {
            grid-template-rows: 15vh 85vh;
        }

        .navbar {
            overflow: hidden;
        }

        .navbar h1 {
            font-size: 5rem;
        }

        .navbar .img-container {
            width: 20rem;
        }

        .sidenav a {
            height: 15rem;
        }
    }
</style>

<script>
    import Controls from "$lib/components/Controls.svelte";
    import { writable } from "svelte/store";
    import { onMount, setContext } from "svelte";
    import {page} from "$app/stores"


    let audioVolume = writable(50)
    setContext("audio-volume", {volume: audioVolume})
</script>