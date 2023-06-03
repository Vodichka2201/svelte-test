<svelte:head>
    <title>Prohozhev Vasya</title>
</svelte:head>

<div class="container">
    <div class="info">
        <div class="animate-background">
            <div class="container-info-container">
                <div class="info-text">
                    <h1>
                        <p class="animate-text-1">Мой сайт.</p>
                        <p class="text-2">Спросите, зачем? Да сам не знаю.</p>
                    </h1>
                </div>
                <h2 class="subtitle">Или же знаю?.</h2>
                <div style="color: black;" class="scroll-button animate-scroll" tabindex="0">
                    <a href="/about">Жми сюда</a>
                    <div class="arrow">&rarr;</div>
                </div>
            </div>
        </div>
    </div>
</div>
<div class="background-div"></div>

<style>
    .subtitle {
        text-align: left;
    }
    .info {
        text-align: center;
        position: relative;
    }
    .info-container {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: left;
        align-items: start;
    }
    .container {
        max-width: 1400px;
        margin: 0;
    }
    .info h1 {
        font-size: 4rem;
        margin: 0;
    }
    .info h1 p {
        position: relative;
        font: inherit;
        margin: 0;
        text-align: left;
        line-height: 130%;
        width: fit-content;
        font-weight: 800;
        letter-spacing: -0.03rem;
    }
    .info h2 {
        max-width: 65ch;
        font-weight: 200;
        margin-top: 0.50rem;
    }
    .background-div {
        background-color: #ecebe8;
        width: 100%;
        height: 56vh;
        margin: -205px auto;
    }
    .info .info-text {
        position: relative;
    }
    .scroll-button {
        display: flex;
        border: none;
        outline: none;
        cursor: pointer;
    }
    .scroll-button .arrow {
        margin-left: 0.50rem;
    }
    .container-info-container {
        padding: 80px;
    }
</style>