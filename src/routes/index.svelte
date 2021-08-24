<script>
    import BeamA from "../beam/BeamA.svelte";

    function windowcloser() {
        window.close();
    }
</script>

<div class="home-page">

    <h1>FREDDY VS AMONG US</h1>

        <div class="container">

            <h2>SELECTOR</h2>
            <button on:click={showBeam}>BEAMER</button>
            <button on:click={windowcloser}>DONT DO IT</button>
            
            <div id="beam-a"><BeamA /></div>
            
            
            <div class="fighters">
                
                <img src="/Fred.png" alt="">
                <img src="/Among.png" alt="">
                
        </div>
    </div>
</div>

<style>
    :global(body) {
    background: linear-gradient(180deg, #000000 0%, rgba(0, 0, 0, 0) 100%);
    background-repeat: no-repeat;
    }

    h1 {
        color: rgb(0, 0, 0);
        background: rgb(255, 0, 0);
        width: 400px;
    }
    img {
        width: 100px;
        margin: auto;
        display: flex;
        justify-content: space-between;
        padding: 5.5rem 5.25rem;
    }
    h2 {
        text-align: center;
        color: red;
    }
    .container {
        background: linear-gradient(180deg, #5D948A 0%, rgba(247, 2, 2, 0) 100%);
        border-radius: 20px;
        width: 600px;
        margin: auto;
    }
    button {
        margin: auto;
        display: flex;
        padding: 5px;
        color: royalblue;
        background: black;
        cursor: pointer;
    }
    #beam-a {
        position: absolute;
        right: 28rem;
        bottom: 370px;
    }
    </style>