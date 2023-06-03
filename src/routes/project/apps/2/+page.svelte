<script>
    
    import Icon from "../../../../component/Icon.svelte";

    let newItem = '';
    let newItem2 = '';
    let list = [];
    function add() {
        if (newItem !== '') {
            list = [
                ...list,
                {
                    Task: newItem,
                    Sum: newItem2,
                    Completed: false,
                },
            ]
            newItem = '';
            newItem2 = '';
        }
    }

    function remove(index) {
        list.splice(index, 1);
        list = list;
    }
</script>


<main>
    <h1>Учёт расходов</h1>

    <form class="form" on:submit|preventDefault={add}>
        <h3>Название</h3>
        <input class="inp" bind:value={newItem} placeholder="Название"/>
        <h3>Сумма</h3>
        <input class="inp2" bind:value={newItem2} placeholder="Сумма"/>
        <button class="addtodo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">
        
        <table class='tablet'>
            <tr>
                <th>Название</th>
                <th>Сумма</th>
                <th>Действия</th>
            </tr>
            {#each list as item, index}
            <tr >
                <td>
                    
                    <div class:completed={item.completed}>
                        {item.Task}
                    </div>
                </td>
                <td>
                    <div class:completed={item.completed}>
                        {item.Sum}
                    </div>
                </td>
                <td> 
                    <button class="delete" on:click={() => remove(index)}>
                        Удалить 
                    </button>
                </td>
                
            </tr>
            {/each}
        </table>

    </div>

</main>


<style>
    .delete {
        background-color: rgb(60, 44, 0);
        color: rgb(255, 234, 177);
    }
    td, th {
        border: solid black 1px ;
    }
    th {
        background-color: rgb(255, 203, 33);
    }
    tr {
        width: 500px;
        text-align: center;
    }
    .tablet{
        border: solid black 2px;
        border-collapse: collapse;
        width: 500px;

    }
    .inp {
        min-width: 500px;
    }
    .inp2 {
        min-width: 500px;
        margin-bottom: 20px;
    }
    .form {
        display: grid;
    }
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background-color: rgb(255, 224, 120);
    }
    form {
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
    }
    input {
        flex-grow: 1;
        width: 0;
        border: none;
        border-bottom: 1px solid black;
        box-shadow: none;
        font-size: 1.2rem;
        margin: 0;
        outline: none;
    }
    .todos {
        width: 100%;
        max-width: 500px;
    }
    .addtodo {
        background-color: rgb(60, 44, 0);
        color: rgb(255, 234, 177);
    }
    h1 {
        text-align: center;
        font-size: 1.5rem;
        margin: 2em 0;
    }
</style>