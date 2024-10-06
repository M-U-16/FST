<button class={mapIsActive==""?"touch-active":"touch-inactive"}
    on:click={reset}
    disabled={mapIsActive==""}
>
    {#if mapIsActive == ""}
    <svg
        xmlns="http://www.w3.org/2000/svg"
        height="24px"
        viewBox="0 -960 960 960" width="24px"
    >
        <path
            d="M419-80q-28 0-52.5-12T325-126L107-403l19-20q20-21 48-25t52 11l74 45v-328q0-17 11.5-28.5T340-760q17 0 29 11.5t12 28.5v472l-97-60 104 133q6 7 14 11t17 4h221q33 0 56.5-23.5T720-240v-160q0-17-11.5-28.5T680-440H461v-80h219q50 0 85 35t35 85v160q0 66-47 113T640-80H419ZM167-620q-13-22-20-47.5t-7-52.5q0-83 58.5-141.5T340-920q83 0 141.5 58.5T540-720q0 27-7 52.5T513-620l-69-40q8-14 12-28.5t4-31.5q0-50-35-85t-85-35q-50 0-85 35t-35 85q0 17 4 31.5t12 28.5l-69 40Zm335 280Z"
        />
    </svg>
    <p>Provinzen mit dem Finger Antippen!</p>
    {:else}
    <svg 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 512 512"
    >
    <path
        fill="none"
        stroke="white"
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="32"
        d="M368 368L144 144M368 144L144 368"
    />
    </svg>
    <p>Auswahl Löschen</p>
    {/if}
</button>
<style>
    button {
        left: 3rem;
        bottom: 3rem;
        border: none;
        display: flex;
        padding: 0.5rem;
        border-radius: 5px;
        position: absolute;
        align-items: center;
        justify-content: space-between;
        color: white;
        font-size: 1rem;
        transition: 0.3s ease;
        cursor: pointer;
    }

    button.touch-active {
        box-shadow: 0px 0px 3px rgb(0, 60, 255);
        background-color: rgb(0, 132, 227);
    }

    button.touch-inactive {
        box-shadow: 0px 0px 3px red;
        background-color: red;
    }

    button svg {
        width: 2rem;
        height: 2rem;
        padding: 0.2rem;
    }
    
    button.touch-active svg {
        fill: white;
        border-radius: 5px;
    }

    button.touch-inactive svg {
        background-color: transparent;
        fill: none;
        stroke: white;
    }

    button:disabled {
        cursor: not-allowed;
    }

    @media (min-height: 2000px) {
        button svg {
            width: 3rem;
            height: 3rem;
            padding: 0.2rem;
        }

        button {
            font-size: 1.5rem;
            bottom: 5rem;
            left: 2rem;
        }
    }
</style>
<script>
    export let reset
    export let mapIsActive = ""
</script>