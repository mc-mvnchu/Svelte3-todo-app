<script>
    let todoItms = [];
    let nnewToddo = '';

    function addTodo() {
        newTodo  = newTodo.trim();
        if (!newTodo) return;

        const todo = {
            text: newTodo,
            checked: false,
            id: Date.now(),
        };

        todoItems = [...tofoItems, todo];
        newTodo = '';
    }
</script>

<style>
    /* component specific styles */
</style>

<main>
    <div class="container">
        <h1 class="app-title">todos</h1>
        <ul class="todo-list"></ul>
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
            placeholder="E.g. Build  a web app"
            />
        </form>
    </div>
</main>