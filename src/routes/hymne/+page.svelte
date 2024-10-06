<div class="container-hymne">
    <h1>Nationalhymne der Niederlande</h1>
    <section class="history">
        <div class="text">
            <h2>Geschichte der Hymne</h2>
            <p>
                <span class="het">'Het Wilhelmus'</span> ist seit 1932 die
                offizielle Nationalhymne der Niederlande.
                Geschrieben wurde der Text zwischen 1568 und
                1572 zu Ehren von Wilhelm I. von Oranien-Nassau.
                Der Autor des Stücks ist unbekannt, jedoch gibt es
                Thesen nach denen Philips van Marnix der Autor gewesen ist.
            </p>
            <p>
                Die Hymne hat 15. Strophen, gesungen werden hauptsächlich
                die erste und zu festlichen Angelegenheiten auch die sechste Strophe.
                Der Anfangsbuchstabe jeder der 15. Strophen bildet
                <b>WILLEM VAN NASSOV</b>. Diese Art von Gedicht heißt Akrostichon.
            </p>
        </div>
        <div class="history-img-container">
            <img src={William} alt="">
            <p>William I., Graf von Oranine</p>
        </div>
    </section>
    <section class="song-texts">
        <div class="fassung">
            <h2>Heute übliche Fassung</h2>
            <div class="strophen-container">
                <div class="strophe">
                    <h3>1. Strophe</h3>
                    <p>
                        Wilhelmus van Nassouwe
                        ben ik, van Duitsen bloed,
                        den vaderland getrouwe
                        blijf ik tot in den dood.
                        Een Prinse van Oranje
                        ben ik, vrij, onverveerd,
                        den Koning van Hispanje
                        heb ik altijd geëerd.
                    </p>
                </div>
                <div class="strophe">
                    <h3>6. Strophe</h3>
                    <p>
                        Mijn schild ende betrouwen
                        zijt Gij, o God mijn Heer,
                        op U zo wil ik bouwen,
                        Verlaat mij nimmermeer.
                        Dat ik doch vroom mag blijven,
                        uw dienaar t'aller stond,
                        de tirannie verdrijven
                        die mij mijn hart doorwondt.
                    </p>
                </div>
            </div>
        </div>
        <div class="fassung">
            <h2>Deutsche Übersetzung</h2>
            <div class="strophen-container">
                <div class="strophe">
                    <h3>1. Strophe</h3>
                    <p>
                        Wilhelmus von Nassau
                        bin ich von deutschem Blut,
                        dem Vaterland treu,
                        bleib ich bis in den Tod.
                        Ein Prinz von Oranien
                        bin ich ganz unverzagt.
                        Den König von Spanien
                        hab ich allzeit geehrt.
                    </p>
                </div>
                <div class="strophe">
                    <h3>6. Strophe</h3>
                    <p>
                        Mein Schild und mein Vertrauen,
                        bist Du o Gott mein Herr,
                        auf Dich so will ich nur bauen,
                        verlass mich nimmermehr,
                        Das ich doch fromm mag bleiben,
                        dir dienen alle Stund,
                        die Tyrannei vertreiben,
                        die mir mein Herz verwundt.
                    </p>
                </div>
            </div>
        </div>
        <!-- <p class="quelle">
            Quelle: https://dutchreview.com/culture/history/history-of-dutch-national-anthem/
        </p> -->
    </section>
    <div class="player-container">
        <img src={hymneImg} alt="hymne">
        <div class="player">
            <button class="refresh" on:click={refresh}>
                <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><path d="M320 146s24.36-12-64-12a160 160 0 10160 160" fill="none" stroke="currentColor" stroke-linecap="square" stroke-miterlimit="10" stroke-width="32"/><path fill="none" stroke="currentColor" stroke-linecap="square" stroke-miterlimit="10" stroke-width="32" d="M256 58l80 80-80 80"/></svg>
            </button>
            <button class="play-pause" on:click={togglePlay}>
                {#if !play}
                <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><path d="M224 432h-80V80h80zM368 432h-80V80h80z"/></svg>
                {:else}
                    <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><path d="M96 448l320-192L96 64v384z"/></svg>
                {/if}
            </button>
            <div class="position-container">
                <div class="position" style:width={percentage.toString()+"%"}></div>
            </div>
        </div>
        <p class="quelle">
            Quelle: https://de.wikipedia.org/wiki/Het_Wilhelmus
        </p>
        <div class="main-margin"></div>
        <audio bind:this={audio} on:timeupdate={timeUpdateCb}>
            <source src="hymne.ogg" type="audio/ogg">
        </audio>
    </div>
</div>

<style>
    .container-hymne {
        display: flex;
        align-items: center;
        overflow-y: scroll;
        width: 100%;
        flex-direction: column;
        margin-left: auto;
        margin-right: auto;

        --default-width: 70%;
    }

    .container-hymne h1 {
        width: var(--default-width);
        font-size: 3rem;
        margin: 1rem 0;
    }

    .container-hymne h2 {
        font-size: 2rem;
    }
    
    .player-container {
        width: var(--default-width);
        display: flex;
        flex-direction: column;
    }

    .player {
        width: 100%;
        display: grid;
        grid-template-columns: auto auto 1fr;
        border: 1px solid black;
        border-bottom: none;
    }
    
    .position-container {
        width: 100%;
        background-color: #f6f6f6;
    }

    .position {
        width: 0;
        height: 100%;
        background-color: #0080ffc6;
    }

    .history {
        display: grid;
        width: var(--default-width);
        grid-template-columns: 1fr 20%;
    }
    
    .history .text {
        line-height: 1.5;
        padding-right: 3rem;
    }

    .history .text p {
        margin-bottom: 1rem;
        font-size: 1.2rem;
    }

    .history-img-container {
        display: flex;
        flex-direction: column;
    } 

    .history-img-container img {
        width: 100%;
        border-radius: 10px 10px 0 0;
        margin: 0;
    }

    .history-img-container p {
        background-color: rgb(238, 238, 238);
        width: 100%;
        padding: 0.5rem;
        font-size: 0.8rem;
        border-radius: 0 0 10px 10px;
        margin: 0;
    }

    .player-container img {
        height: 400px;
        width: 600px;
        object-fit: cover;
    }

    button {
        width: 5rem;
        height: 5rem;
        padding: 1rem;
        cursor: pointer;
        border: none;
        background-color: rgb(255, 255, 255);
    }
    button:hover {
        background-color: rgb(244, 244, 244);
    }
    button svg {
        width: 100%;
        height: 100%;

    }

    .play-pause {
        border-left: 1px solid black;
        border-right: 1px solid black;
    }

    .refresh {
        transform: rotate(-270deg);
    }

    .quelle {
        color: rgb(98, 98, 98);
        border: 1px solid grey;
        font-size: 1.2rem;
        display: flex;
        justify-content: center;
        padding: 0.2rem;
    }

    .song-texts {
        display: grid;
        gap: 4rem;
        grid-template-columns: 1fr 1fr;
        flex-direction: column;
        width: 100%;
        max-width: var(--default-width);
        margin-top: 3rem;
    }

    .song-texts .fassung .strophe {
        padding: 1rem 2rem 1rem 0;
    }

    .het {
        font-style: italic;
    }

    @media (min-width: 2000px) {
        .history {
            display: grid;
            grid-template-columns: 1fr 30%;
        }

        .history .text p {
            font-size: 2.5rem;
        }

        .container-hymne {

            --default-width: 50%;
        }

        .container-hymne h1 {
            font-size: 5rem;
        }

        .container-hymne h2 {
            font-size: 4rem;
        }
    }
</style>

<script>
    import hymneImg from "$lib/images/hymne.jpg"
    import William from "$lib/images/William_I_of_Orange.jpg"
    import { getContext } from "svelte";
    const { volume } = getContext("audio-volume")

    let audio
    let play = false
    let percentage = 0
    /* let position, duration */

    $: audio?audio.volume=$volume/100:null

    function togglePlay() {
        play = !play
        if (play) {
            audio.play()
        } else {
            audio.pause()
        }
    }

    function toAudioTimestamp(seconds) {
        let result = ""
        let minutes = parseInt(seconds / 60)
        let secs = Math.ceil(seconds % 60)
        if (minutes < 10) {
            result += "0"
        }
        result += minutes.toString()
        result += ":"
        if (secs < 10) {
            result += "0"
        }
        result += secs.toString()
        return result
    }

    function getTimePercent(num1, num2) {
        return ((num1/num2)*100).toFixed(2)
    }

    function timeUpdateCb() {
        percentage = getTimePercent(
            audio.currentTime,
            audio.duration
        )
    }

    function refresh() {
        audio.currentTime = 0
        audio.pause()
        play = false
    }
</script>