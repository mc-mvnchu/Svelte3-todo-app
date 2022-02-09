<script>
    let todoItems = [];
    let newTodo = '';

    function addTodo() {
        newTodo = newTodo.trim();
        if (!newTodo) return;

        const todo = {
            text: newTodo,
            checked: false,
            id: Date.now(),
        };

        todoItems = [...todoItems, todo];
        newTodo = '';
    }
    
</script>

<style>
    /* component specific styles */
</style>

<main>
    <div class="container">
        <h1 class="app-title">todos</h1>
        <ul class="todo-list">
            <!-- #each todoItems as todo (todo.id) -->
            <li class="todo-item">
                <input id={todo.id} type="checkbox" />
                <label for={todo.id} class="tick"></label>
                <span>{todo.text}</span>
                <button class="delete-todo">
                    <svg><use href="#delete-icon"></use></svg>
                </button>
            </li>
            <!-- {/each} -->
        </ul>
        <div class="empty-state">
            <svg class="checklist-icon">
                <use href="#checklist-icon"></use>
            </svg>
            <h2 class="empty-state__title">Add your first todo</h2>
            <p class="empty-state__description">What do you want to get done today?</p>
        </div>
        <form on:submit|preventDefault={addTodo}>
            <input
            class="js-todo-input"
            type="text"
            aria-label="Enter a new todo item"
            placeholder="E.g. Build a web app"
            />
        </form>
    </div>
</main>