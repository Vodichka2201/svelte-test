<script>
    
    import Icon from "../../../../component/Icon.svelte";

    let newItem = '';
    let todoList = [];
    function add() {
        if (newItem !== '') {
            todoList = [
                ...todoList,
                {
                    Task: newItem,
                    Completed: false,
                },
            ]
            newItem = '';
        }
    }

    function remove(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }
    function complete(index) {
        todoList[index].Completed = !todoList[index].Completed;
    }
</script>


<main>
    <h1>Мой лист</h1>
    <form on:submit|preventDefault={add}>
        <input bind:value={newItem} placeholder="Enter todo"/>
        <button class="add-todo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">

        {#each todoList as item, index}
        <div class="todo" class:completed={item.completed}>
            <span class="todo_text">{item.Task}</span>
            <div class="todo_buttons">
                <button class="complete" on:click={() => complete(index)}>
                    <Icon name="check-mark"/>
                </button>
                <button class="delete" on:click={() => remove(index)}>
                    <Icon name="delete"/>
                </button>
            </div>
        </div>
        {/each}
    </div>
</main>


<style>
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
    .todo {
        display: flex;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 15px rgb(0, 0, 0 / 20%);
        background-color: hsla(0, 0%, 100%, 0.2);
        margin-top: 1rem;
        font-size: 1.2rem;
        justify-content: space-between;
        align-items: center;
    }
    .todo_buttons {
        display: flex;
        align-items: center;
        margin-left: 1rem;
    }
    .todo_button {
        width: 32px;
        height: 32px;
        padding: 4px;
        margin: 0;
        flex-shrink: 0;
    }

    h1 {
        text-align: center;
        font-size: 1.5rem;
        margin: 2em 0;
    }
</style>