<button on:click={close}>
    <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 512 512"
    >
        <path
            fill="none"
            stroke="white"
            stroke-linecap="square"
            stroke-miterlimit="10"
            stroke-width="48"
            d="M184 112l144 144-144 144"
        />
    </svg>
</button>

<style>
    button {
        width: 3rem;
        height: 3rem;
        position: absolute;
        background-color: rgb(0, 0, 0);
        top: 50%;
        transform: translateY(-50%);
        left: -1.5rem;
        border-radius: 50%;
        padding: 0.5rem;
        border: none;
        cursor: pointer;
    }

    svg {
        width: 100%;
        height: 100%;
    }
</style>

<script>
import { createEventDispatcher } from "svelte";
const dispatcher = createEventDispatcher()

function close() {
    dispatcher("close", {})
}
</script>