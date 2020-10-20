<template>
<div class="todo-list">
    <template v-for="todo in todos" :key="todo.key">
        <todo-item :todo="todo" />
    </template>
</div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
    props: {
        todos: {
            type: Array,
        },
    },
    setup(props) {
        const todos = props.todos;

        return {
            todos,
        };
    },
    components: {
        TodoItem,
    },
};
</script>

<style scoped>
.todo-list {
    display: grid;
    row-gap: 14px;
}
</style>
