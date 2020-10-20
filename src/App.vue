<template>
<main>
    <div class="container">
        <h1>待办事项</h1>
        <todo-add :tid="todos.length" @addOneTodo="addTodo" />
        <todo-filter />
        <todo-list :todos="todos" />
    </div>
</main>
</template>

<script>
import {
    ref
} from "vue";
import TodoAdd from "./components/TodoAdd.vue";
import TodoFilter from "./components/TodoFilter.vue";
import TodoItem from "./components/TodoItem.vue";
import TodoList from "./components/TodoList.vue";
export default {
    name: "App",
    setup() {
        // 存储todolist
        const todos = ref([]);
        const addTodo = (todo) => {
            todos.value.push(todo.value);
        };

        return {
            todos,
            addTodo,
        };
    },
    components: {
        TodoAdd,
        TodoFilter,
        TodoItem,
        TodoList,
    },
};
</script>

<style scoped>
main {
    height: 100vh;
    width: 100vw;
    display: grid;
    align-items: start;
    justify-items: center;

    background-color: rgb(203, 210, 240);
}

.container {
    width: 60%;
    max-width: 400px;
    display: block;
    box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.15);
    border-radius: 24px;
    padding: 24px 18px;
    background-color: rgb(245, 246, 252);
    padding: 48px 28px;
    margin: 100px 0;
    overflow: auto;
}

h1 {
    margin: 24px 0;
    font-size: 28px;
    color: #414873;
}
</style>
