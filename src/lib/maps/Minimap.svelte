<div class="minimap">
    <img src={img} alt="province">
</div>

<style>
    .minimap {
        width: 10rem;
        height: 10rem;
        background-color: rgb(0, 0, 0);
        border: 3px solid rgb(0, 0, 0);
    }

    img {
        height: 100%;
        width: 100%;
        object-fit: contain;
        padding: 0.5rem;
    }
</style>

<script>
    export let img
</script>