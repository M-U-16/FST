<div class="flag-container">
    <img src={src} alt="">
    <div>
        <p>{type} von {name}</p>
    </div>
</div>
<style>
    .flag-container {
        display: flex;
        width: 33rem;
        border: 2px solid rgb(99, 99, 99);
        border-radius: 10px;
        overflow: hidden;
        align-items: center;
        background-color: var(--app-grey);
    }
    
    .flag-container img {
        width: 15rem;
        object-fit: cover;
    }
    
    .flag-container div {
        height: 100%;
    }
    
    .flag-container p {
        font-size: 2.5rem;
        height: 100%;
        padding: 1rem;
    }
</style>
<script>
    export let src
    export let type
    export let name
</script>