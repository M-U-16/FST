<div class="controls" style:transform={crontrolsActive?"translateX(10px)":`translateX(-${closeControlsWidth*2}px)`}>
    <button class="sound" on:click={toggleSlider}>
        <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none" viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="black"
        >
            <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M19.114 5.636a9 9 0 0 1 0 12.728M16.463 8.288a5.25 5.25 0 0 1 0 7.424M6.75 8.25l4.72-4.72a.75.75 0 0 1 1.28.53v15.88a.75.75 0 0 1-1.28.53l-4.72-4.72H4.51c-.88 0-1.704-.507-1.938-1.354A9.009 9.009 0 0 1 2.25 12c0-.83.112-1.633.322-2.396C2.806 8.756 3.63 8.25 4.51 8.25H6.75Z"
            />
        </svg>
    </button>
    <button class="full-screen" on:click={toggleFullscreen}>
        <svg 
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 512 512"
        >
            <path
                d="M336 448h56a56 56 0 0056-56v-56M448 176v-56a56 56 0 00-56-56h-56M176 448h-56a56 56 0 01-56-56v-56M64 176v-56a56 56 0 0156-56h56"
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="32"
            />
        </svg>
    </button>
    <button
        class="close-controls"
        on:click={toggleControls}
        bind:offsetHeight={closeControlsWidth}
        style:transform={crontrolsActive?"rotate(180deg)": "rotate(0)"}
    >
        <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 512 512"
        >
            <path
                fill="none"
                stroke="black"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="48"
                d="M184 112l144 144-144 144"
            />
        </svg>
    </button>
    <div class="sound-slider{sliderActive?" sound-slider-active":""}">
        <input
            bind:this={audioInput}
            type="range"
            orient="vertical"
            on:input={audioChange}
        >
        <p>{$volume}</p>
    </div>
</div>

<style>
    .controls {
        left: 0;
        bottom: 1rem;
        display: flex;
        height: 2.5rem;
        position: fixed;
        border-radius: 5px;
        background-color: var(--app-grey);
        transition: transform 0.4s ease;
    }

    .controls button {
        height: 100%;
        border: none;
        cursor: pointer;
        aspect-ratio: 1;
        padding: 0.45rem;
        position: relative;
        background-color: transparent;
    }
    
    .controls button svg {
        width: 100%;
        height: 100%;
    }
    
    .controls button:active {
        transition: transform 0.3s ease;
    }

    .sound-slider {
        position: absolute;
        bottom: 100%;
        left: 0;
        transform: translateY(3px);
        background-color: #dbdbdb61;
        padding: 0.75rem;
        border-radius: 5px;
        width: 2.5rem;
        display: flex;
        align-items: center;
        opacity: 0;
        pointer-events: none;
        transition: 0.3s ease;
        flex-direction: column;
    }

    .sound-slider p {
        font-size: 12px;
    }

    .sound-slider.sound-slider-active {
        pointer-events: all;
        transform: translateY(-2px);
        opacity: 1;
    }

    .sound-slider input {
        writing-mode: vertical-lr;
        direction: rtl;
        width: 16px;
        vertical-align: bottom;
    }
</style>

<script>
    export let volume
    
    let audioInput
    let fullscreen = false
    let sliderActive = false
    let closeControlsWidth = 0
    let crontrolsActive = false
    
    function closeSlider() {
        sliderActive = false
    }

    function toggleSlider() {
        sliderActive = !sliderActive
    }

    function toggleControls() {
        closeSlider()
        crontrolsActive = !crontrolsActive
    }

    function toggleFullscreen() {
        
        if (!fullscreen) {
            document.documentElement
            .requestFullscreen()
        } else {
            document.exitFullscreen()
            .then(()=>console.log("disabled full screen mode"))
            .catch((error)=>console.error(error))
        }

        fullscreen = !fullscreen
    }

    function audioChange() {
        if (audioInput) {
            volume.set(audioInput.value)
            
        }
    }
</script>