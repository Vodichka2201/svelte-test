<svelte:head>
    <title>Portfolio</title>
</svelte:head>

<div class="container">
    <h1>Мои проекты</h1>
    <div class="apps">
        <div class="app">
            {#each routes as page}
                <h2>{page.title}</h2>
                <p>{page.body}</p>
                <p class="readmore">
                    <a class="link" href={`/project/apps/${page.id}`}>Читать больше</a>
                </p>
            {/each}
        </div>
    </div>
    <h1>Учёт расходов</h1>
    <div class="apps">
        <div class="app">
            {#each cost as cos}
                <h2>{cos.title}</h2>
                <p>{cos.body}</p>
                <p class="readmore">
                    <a class="link" href={`/project/apps/${cos.id}`}>Читать больше</a>
                </p>
            {/each}
        </div>
    </div>
</div>

<script>
    import {routes} from "./routes.js";
    import {cost} from "./costaccounting.js";
</script>

<style>
    .container {
        margin: 50px auto;
        max-width: 800px;
        padding: 0 20px;
    }
    .apps {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }
    .app {
        border: 1px solid #ddd;
        padding: 10px;
        box-shadow: 0 0 10px #eee;
    }
    .link {
        color: rgb(10, 10, 139);
    }
</style>